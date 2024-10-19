<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Bristol Talks</title>
    <style>
        body {
            font-family: 'Comic Sans MS', cursive, sans-serif;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            height: 100vh;
            margin: 0;
            background-color: #000;
            color: #00ffff;
            border: 10px solid #00ffff;
            border-radius: 15px;
            box-shadow: 0 0 20px rgba(0, 255, 255, 0.5);
            padding: 20px;
            overflow: hidden;
        }
        #clickButton {
            background-color: #00f;
            color: white;
            border: none;
            padding: 30px;
            font-size: 20px;
            cursor: pointer;
            border-radius: 30px;
            transition: all 0.3s ease;
            box-shadow: 0 4px 8px rgba(0, 0, 255, 0.5);
            max-width: 80%;
            white-space: normal;
            position: absolute;
        }
        #clickButton:active {
            background-color: #1e90ff;
            transform: scale(0.95);
        }
    </style>
</head>
<body>
    <h1 style="position: fixed; top: 10px; left: 10px; color: #00ffff;">Bristol Talks</h1>
    <button id="clickButton">Click Me!</button>

    <script>
        const facts = [
            "Home of ESPN 🎥 – Bristol is famous for being the headquarters of the sports broadcasting giant, ESPN, since 1979.",
            "Birthplace of the American clock industry 🕰️ – In the 19th century, Bristol was a leading hub for clock manufacturing!",
            "Mum City USA 🌸 – Bristol hosts the annual Mum Festival, celebrating chrysanthemums, since 1962.",
            "Lake Compounce 🎢 – The nation’s oldest operating amusement park, Lake Compounce, has been thrilling visitors since 1846.",
            "Haunted rides? 👻 – The Wildcat coaster at Lake Compounce is rumored to have supernatural occurrences at night!",
            "Population Trivia – Bristol has about 60,000 residents, giving it a small-town vibe but city-like amenities.",
            "The Clock Museum 🕰️ – The American Clock & Watch Museum in Bristol has over 1,500 timepieces on display.",
            "The Bristol Press 🗞️ – Bristol's local newspaper has been in print since 1871.",
            "Native Roots – Before Europeans arrived, the Tunxis Native American tribe inhabited the area.",
            "World War I Doughboy Statue 🪖 – The statue on Memorial Boulevard is a Bristol landmark.",
            "ESPN’s quirky beginning 🎥 – ESPN was originally housed in an abandoned bowling alley!",
            "Favorite pastimes – Hiking and kayaking around Birge Pond and Rockwell Park are popular among locals.",
            "Terryville is close by – And it hosts the famous Terryville Fair!",
            "Bristol Eastern vs. Bristol Central rivalry 🏈 – The two high schools' annual Thanksgiving football game is legendary.",
            "Fun Fact – ESPN’s first broadcast ever was a slow-pitch softball game.",
            "Birthplace of Aaron Hernandez – Former NFL player, Aaron Hernandez, grew up here.",
            "Diverse wildlife – You can spot deer, foxes, and even the occasional black bear in the area.",
            "Pequabuck River 🏞️ – This river flows through Bristol and is great for peaceful fishing.",
            "Bristol's Nickname – It's often referred to as the “All Heart City.”",
            "Culinary Delight – Locals rave about the grinders at Parkside Café.",
            "Old-school diners – The Bristol Diner is the place to go for a classic breakfast.",
            "Muzzy Field ⚾ – This historic stadium opened in 1914 and has hosted Babe Ruth himself!",
            "ESPN’s Annual Cornhole Tournament – Yes, even ESPN loves some backyard games!",
            "Green spaces galore 🌳 – Bristol boasts over 730 acres of parks and public spaces.",
            "Main Street charm – It’s home to quaint shops and restaurants worth exploring.",
            "Home to a creepy museum 🦴 – The New England Carousel Museum has antique carousels and organ pieces.",
            "Former copper mine town 🛠️ – In the 18th century, copper mining was active here.",
            "Annual Mum Festival Parade 🌼 – Expect floats, marching bands, and lots of mums each September.",
            "The Carousel Museum is haunted? 👻 – Some visitors claim to have seen ghostly carousel figures moving!",
            "Unusual sports facilities – Bristol has a soapbox derby track.",
            "Frequent snowfall ❄️ – Bristol gets about 37 inches of snow each year!",
            "Known for fall foliage 🍂 – Bristol’s hills turn stunning shades of red, orange, and yellow each autumn.",
            "Rockwell Park 🏞️ – A perfect blend of trails, a splash pad, and playgrounds for families.",
            "Samuel Clock Factory 🕰️ – The company behind the popular Ansonia clocks started here.",
            "Celebrity spotting – Joey Logano, the NASCAR driver, grew up in nearby Middletown and often visits Bristol.",
            "Cupcake heaven – Café Real serves some of the most Instagram-worthy cupcakes in town.",
            "Bike-friendly paths 🚴 – The Farmington Canal Heritage Trail passes close to Bristol.",
            "Bristol Boys and Girls Club – A key part of the community since 1907.",
            "4th of July Fireworks Extravaganza 🎆 – An annual must-see at Rockwell Park.",
            "Public art everywhere 🎨 – Spot murals across town, promoting the arts and culture scene.",
            "Maple Syrup Festival 🍁 – Held every March, showcasing Connecticut’s syrup-making tradition.",
            "Birthplace of Jerry Springer’s Wife 💍 – Yup, his wife, Micki Velton, came from Bristol!",
            "Friendly debates – Locals argue passionately over who has the best pizza in town.",
            "Grew up here – Benny Davis, the songwriter of “Baby Face,” hailed from Bristol.",
            "Mural Mania 🎨 – Bristol has a booming street art movement.",
            "Fishing Tournaments – You can enter Pequabuck River fishing tournaments annually!",
            "Best sledding spots 🛷 – Casey Field becomes a sledding paradise every winter.",
            "Local farmers markets 🥕 – Fresh produce is available every Sunday morning in summer.",
            "Muzzy Field Legends – This field once hosted games with Babe Ruth and the Boston Red Sox!",
            "Local breweries 🍺 – You’ll find delicious craft beers at Firefly Hollow Brewing.",
            "Yankee Peddler tradition – A 200-year-old farmers market still operates in nearby Canton.",
            "Parks with hidden gems – Check out Hoppers-Birge Pond Nature Preserve for a peaceful stroll.",
            "Skateboard scene 🛹 – Rockwell Skate Park is a local favorite for skaters.",
            "Roller Disco Nights 🎵 – Spare Time Bristol sometimes hosts 80s-themed roller skating events.",
            "Family traditions – Every year, thousands gather for the city’s Christmas on the Common event.",
            "Snow day fun – Casey Field transforms into a sledding haven after snowstorms!",
            "Rare book finds 📚 – The Bristol Public Library has some incredible antique book collections.",
            "Olde-school drive-ins 🍔 – Try the Time Out Grill, one of the few surviving drive-in diners.",
            "Haunted history? 👻 – Locals swear that ghostly figures haunt the older homes along Federal Hill.",
            "Friendly rivalry with Southington – Which town has the better apple festival? Locals love to debate it.",
            "Annual Arts Festival 🎭 – Bristol is full of galleries and events showcasing local art every spring.",
            "DIY flower bouquets 🌻 – Head to Buttonwood Farm for pick-your-own flowers.",
            "Best diner food in the area? – George's Terryville Diner is only a short drive away.",
            "Bristol Historical Society – Discover more about Bristol’s rich history here.",
            "Local crafts 🎨 – The Artisans Boutique at Bristol's annual fairs showcases amazing local talent.",
            "Bristol’s downtown renovation – Revitalization projects have brought new life to downtown Bristol.",
            "National Youth Sports Day – Bristol hosts multiple youth sports events each summer.",
            "Community theatre 🎭 – The Bristol Theatre Group hosts productions loved by the entire community.",
            "Firefly Night Hike – Join a guided night hike through Hoppers-Birge Pond to see fireflies.",
            "Classic car shows 🚗 – Don’t miss the annual Classic Car Show on Memorial Boulevard.",
            "‘Dinner on Main Street’ 🍽️ – Every summer, local restaurants set up tables for a community-wide outdoor dinner.",
            "Antique Trail – Bristol’s antique shops offer everything from clocks to vintage furniture.",
            "All Heart Pop-up Market ❤️ – Supporting local vendors, this market happens quarterly at the Bristol Event Center.",
            "Mum Flower Maze 🌼 – Created for the Mum Festival, it’s an annual favorite for families.",
            "Rockwell Park Summer Festival – Rockwell Park hosts a huge summer event with live music, food trucks, and games.",
            "Haunted Hayride – Join the spooky fun every October at Cedar Hill Farm.",
            "Bristol’s Holiday Lights Tour 🎄 – Every winter, locals decorate homes and neighborhoods, creating a holiday wonderland.",
            "Soapbox Derby Races – Kids and adults alike enjoy soapbox derby races during the summer at the local track.",
            "Bristol Hometown Hero Program – Recognizing residents for their community service and volunteerism.",
            "Yoga in the Park 🧘 – Free summer yoga classes are hosted in Rockwell Park on Sunday mornings.",
            "Live Jazz Nights 🎷 – Enjoy live jazz music at local Bristol cafes every Thursday night.",
            "New England Carousel Museum Family Day – Free admission and activities for the whole family one Sunday each month.",
            "Beer and Chili Festival 🌶️🍺 – An annual fall event that combines craft beer with the best local chili recipes.",
            "Bristol River Cleanup Day – Residents gather each April to clean up the Pequabuck River and surrounding areas.",
            "Hot Air Balloon Festival 🎈 – See dozens of hot air balloons take flight every August at the Bristol Hot Air Balloon Fest.",
            "Farmers Market Cooking Demos 👩‍🍳 – Local chefs demonstrate how to cook with fresh market produce.",
            "Federal Hill Historic District – Take a walking tour of the historic homes in this beautiful area.",
            "Kayaking Adventures 🛶 – Enjoy group kayaking adventures on the Pequabuck River organized by local outfitters.",
            "Open Mic Night – Share your talents every first Friday at the Bristol Arts Café.",
            "Downtown Scarecrow Competition 🎃 – Businesses compete in creating the best scarecrow display in October.",
            "Seasonal Ice Skating – Visit Rockwell Park for outdoor ice skating during the winter months.",
            "Bristol’s Annual Street Painting Festival 🎨 – Artists fill downtown sidewalks with colorful chalk murals each spring.",
            "Community Mural Project – Residents of all ages come together to paint murals that reflect Bristol’s history and diversity.",
            "Wildflower Walks 🌼 – Learn about native plants on guided walks in the Hoppers-Birge Pond Nature Preserve.",
            "Outdoor Movie Nights 🎬 – Free family-friendly movies are shown on a big screen at Rockwell Park throughout the summer.",
            "Vintage Baseball Game ⚾ – Watch a reenactment of a 19th-century baseball game at Muzzy Field.",
            "Federal Hill Ghost Tour 👻 – Learn the spooky stories and haunted history of Federal Hill on this nighttime walking tour.",
            "Nature Photography Meetup 📸 – Join fellow photographers for a nature shoot in one of Bristol’s scenic parks.",
            "Book Club in the Park 📖 – The Bristol Public Library hosts monthly book clubs at various parks.",
            "Trail Maintenance Volunteer Day 🛠️ – Help maintain the beauty of Bristol’s trails with the Parks and Recreation Department.",
            "Local Artist Spotlight 🌟 – Every month, Bristol showcases a different local artist at the library’s gallery.",
            "Community Gardens 🍅 – Grow your own vegetables at the community garden plots available throughout Bristol.",
            "Bristol Block Party 🎉 – Bristol hosts block parties throughout the summer with food, music, and games.",
            "Cider Fest 🍎 – Celebrate the harvest season with freshly pressed cider, apple treats, and family fun in the fall.",
            "Stargazing at Indian Rock 🌌 – A guided astronomy event at the Indian Rock Nature Preserve to learn about constellations.",
            "Classic Arcade Night 🕹️ – Relive the 80s with a night at a pop-up classic arcade in the heart of Bristol.",
            "Local Honey Tasting 🍯 – Sample different varieties of honey from Bristol-area beekeepers.",
            "Bristol’s Kite Festival 🪁 – Fly your kites at this family-friendly event held every spring at Rockwell Park.",
            "Veterans Parade 🇺🇸 – Every November, the city honors veterans with a parade down Main Street.",
            "Terryville Tunnel Legends 🚂 – Explore the old Terryville railroad tunnel rumored to be haunted.",
            "Pie Eating Contest 🥧 – The Mum Festival pie-eating contest is one of the most entertaining events of the year!",
            "Bristol Photography Contest 📸 – An annual contest that invites community members to capture Bristol’s beauty through their lens.",
            "Pumpkin Palooza 🎃 – A fall celebration with pumpkin carving, a costume contest, and family-friendly activities.",
        ];

        let currentFactIndex = 0;
        const button = document.getElementById('clickButton');

        button.addEventListener('click', () => {
            button.textContent = facts[currentFactIndex];
            currentFactIndex = (currentFactIndex + 1) % facts.length;
            moveButtonRandomly();
        });

        function moveButtonRandomly() {
            const x = Math.random() * (window.innerWidth - button.clientWidth);
            const y = Math.random() * (window.innerHeight - button.clientHeight);
            button.style.left = `${x}px`;
            button.style.top = `${y}px`;
        }
    </script>
</body>
</html>
