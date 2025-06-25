<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>VENY Simulations Limited</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Google Fonts - Inter -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'Inter', sans-serif;
        }
        /* Hide all sections by default, JavaScript will show the active one */
        .page-section {
            display: none;
        }
        .page-section.active {
            display: block;
        }
        /* Basic styling for collapsible lists */
        .collapsible-header {
            cursor: pointer;
            @apply flex justify-between items-center bg-gray-100 p-2 rounded-md mb-1;
        }
        .collapsible-header:hover {
            @apply bg-gray-200;
        }
        .collapsible-content {
            display: none;
            @apply pl-4 border-l border-gray-300 ml-2;
        }
        .collapsible-content.expanded {
            display: block;
        }
        .collapsible-header .arrow::before {
            content: '►'; /* Right arrow for collapsed */
            display: inline-block;
            transition: transform 0.2s ease-in-out;
        }
        .collapsible-header.expanded .arrow::before {
            content: '▼'; /* Down arrow for expanded */
            transform: rotate(90deg);
        }
        .loading-spinner {
            border: 4px solid #f3f3f3; /* Light grey */
            border-top: 4px solid #3498db; /* Blue */
            border-radius: 50%;
            width: 20px;
            height: 20px;
            animation: spin 1s linear infinite;
            display: inline-block;
            vertical-align: middle;
            margin-right: 8px;
        }
        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }
    </style>
</head>
<body class="bg-gray-100 flex flex-col items-center justify-start min-h-screen p-4">

    <!-- Navigation Bar -->
    <nav class="w-full max-w-4xl bg-white p-4 rounded-xl shadow-lg mb-6 flex justify-center space-x-6">
        <button class="nav-link text-blue-600 hover:text-blue-800 font-semibold text-lg" data-target="home">Home</button>
        <button class="nav-link text-blue-600 hover:text-blue-800 font-semibold text-lg" data-target="content">Content</button>
        <button class="nav-link text-blue-600 hover:text-blue-800 font-semibold text-lg" data-target="links">Links and Resources</button>
    </nav>

    <!-- Main Content Area -->
    <div class="bg-white p-8 rounded-xl shadow-lg max-w-4xl w-full text-center">

        <!-- Home Page Section -->
        <div id="home" class="page-section active">
            <!-- Header Image -->
            <img src="https://placehold.co/600x400/000000/FFFFFF?text=openBVE+Image+Placeholder"
                 alt="openBVE Simulation Screenshot"
                 class="w-full h-auto rounded-lg mb-6 shadow-md"
                 onerror="this.src='https://placehold.co/600x400/CCCCCC/000000?text=Image+Not+Found';">

            <!-- Website Title -->
            <h1 class="text-4xl font-bold text-gray-800 mb-6 rounded-md p-2 bg-blue-100 shadow-sm">
                VENY Simulations Limited
            </h1>

            <!-- Short Description -->
            <p class="text-gray-600 text-lg mb-8">
                Welcome to VENY Simulations, where innovation meets realistic experiences.
                We specialize in cutting-edge simulation solutions.
            </p>

            <!-- Hyperlink Button -->
            <a href="https://venysimulations.com/home"
               class="inline-block bg-blue-600 hover:bg-blue-700 text-white font-semibold py-3 px-8 rounded-full transition duration-300 ease-in-out transform hover:scale-105 shadow-md">
                Visit Our Home Page
            </a>
        </div>

        <!-- Content Page Section -->
        <div id="content" class="page-section text-left">
            <h2 class="text-3xl font-bold text-gray-800 mb-6 pb-2 border-b-2 border-blue-400">Content</h2>

            <!-- Rolling Stock Section -->
            <div class="mb-6">
                <div class="collapsible-header text-xl font-semibold text-gray-700 rounded-lg p-3 shadow-sm" data-target-content="rolling-stock">
                    Rolling Stock <span class="arrow"></span>
                </div>
                <div id="rolling-stock" class="collapsible-content">
                    <!-- LLM Feature for Rolling Stock Facts -->
                    <div class="my-4 p-4 bg-purple-50 rounded-lg shadow-inner text-center">
                        <button id="generateFactBtn"
                                class="inline-flex items-center bg-purple-600 hover:bg-purple-700 text-white font-semibold py-2 px-6 rounded-full transition duration-300 ease-in-out transform hover:scale-105 shadow-md">
                            ✨ Generate a Rolling Stock Fact ✨
                        </button>
                        <div id="factDisplay" class="mt-4 text-gray-700 text-base italic">
                            Click the button above to discover a fun fact about our rolling stock!
                        </div>
                        <div id="loadingIndicator" class="hidden mt-4">
                            <span class="loading-spinner"></span> Generating fact...
                        </div>
                    </div>
                    <!-- End LLM Feature -->

                    <!-- MTA New York City Subway -->
                    <div class="collapsible-header text-lg font-medium text-gray-600 mt-2" data-target-content="mta-nycs">
                        MTA New York City Subway <span class="arrow"></span>
                    </div>
                    <ul id="mta-nycs" class="collapsible-content list-disc pl-5 mt-1 space-y-1">
                        <li>
                            <div class="collapsible-header text-md font-normal text-gray-500" data-target-content="mta-a-div">
                                Subpage - A Division <span class="arrow"></span>
                            </div>
                            <ul id="mta-a-div" class="collapsible-content list-circle pl-5 mt-1 space-y-0.5 text-sm">
                                <li>R62 [Kawasaki] 1301-1625</li>
                                <li>R62A [Bombardier] 1651-2475</li>
                                <li>R142 [Bombardier] 1101-1250, 6301-7180</li>
                                <li>R142A [Kawasaki] 7591-7810</li>
                                <li>R152 [Kawasaki] 1511-2375</li>
                                <li>R188 [Kawasaki]
                                    <ul class="list-square pl-5">
                                        <li>7211-7590 [Former R142A]</li>
                                        <li>7811-7936 [Factory-Built]</li>
                                    </ul>
                                </li>
                            </ul>
                        </li>
                        <li>
                            <div class="collapsible-header text-md font-normal text-gray-500" data-target-content="mta-b-div">
                                Subpage - B Division <span class="arrow"></span>
                            </div>
                            <ul id="mta-b-div" class="collapsible-content list-circle pl-5 mt-1 space-y-0.5 text-sm">
                                <li>R143 [Kawasaki] 8101-8312</li>
                                <li>R153
                                    <ul class="list-square pl-5">
                                        <li>R153A, Base Order:
                                            <ul class="list-disc pl-5">
                                                <li>Five Car: 3060-3549</li>
                                                <li>Four Car: 3550-3637</li>
                                            </ul>
                                        </li>
                                        <li>R153A, Supplemental Order: 3638-3757</li>
                                        <li>R153A, Option Order 1:
                                            <ul class="list-disc pl-5">
                                                <li>Five Car: 3758-3887</li>
                                                <li>Four Car: 3888-4002</li>
                                            </ul>
                                        </li>
                                        <li>R153T, Gangway: 3040-3059</li>
                                    </ul>
                                </li>
                                <li>R160A [Alstom]
                                    <ul class="list-square pl-5">
                                        <li>Four Car: 8313-8652, 9943-9974</li>
                                        <li>Five Car: 8653-8712, 9233-9802</li>
                                    </ul>
                                </li>
                                <li>R160B [Kawasaki]
                                    <ul class="list-square pl-5">
                                        <li>Alstom, Five Car: 8713-8842, 9803-9942</li>
                                        <li>Siemens, Five Car: 8843-9102</li>
                                    </ul>
                                </li>
                                <li>R179 [Bombardier]
                                    <ul class="list-square pl-5">
                                        <li>Five Car: 3010-3049, 3238-3327</li>
                                        <li>Four Car: 3050-3237</li>
                                    </ul>
                                </li>
                                <li>R211 [Kawasaki]
                                    <ul class="list-square pl-5">
                                        <li>R211A, Option Order 1: 3400-4039</li>
                                        <li>R211A, Base Order: 4060-4499</li>
                                        <li>R211T: 4040-4059</li>
                                    </ul>
                                </li>
                            </ul>
                        </li>
                        <li>
                            <div class="collapsible-header text-md font-normal text-gray-500" data-target-content="sir-div">
                                Subpage - SIR Division <span class="arrow"></span>
                            </div>
                            <ul id="sir-div" class="collapsible-content list-circle pl-5 mt-1 space-y-0.5 text-sm">
                                <li>R44 [St. Louis] 388–435, 436–466 (even)</li>
                                <li>R153S [Kawasaki] 200-274</li>
                                <li>R211S [Kawasaki] 100-174</li>
                            </ul>
                        </li>
                        <li>
                            <div class="collapsible-header text-md font-normal text-gray-500" data-target-content="lirr-div">
                                Subpage - Long Island Railroad (LIRR) <span class="arrow"></span>
                            </div>
                            <ul id="lirr-div" class="collapsible-content list-circle pl-5 mt-1 space-y-0.5 text-sm">
                                <li>M1 [Budd]</li>
                                <li>M3 [Budd]</li>
                                <li>M7 [Bombardier]</li>
                                <li>M9 [Kawasaki]</li>
                            </ul>
                        </li>
                        <li>
                            <div class="collapsible-header text-md font-normal text-gray-500" data-target-content="mnrr-div">
                                Subpage - Metro-North Railroad (MNRR) <span class="arrow"></span>
                            </div>
                            <ul id="mnrr-div" class="collapsible-content list-circle pl-5 mt-1 space-y-0.5 text-sm">
                                <li>M1A [Budd]</li>
                                <li>M2</li>
                                <li>M3A [Budd]</li>
                                <li>M4</li>
                                <li>M6</li>
                                <li>M7A [Bombardier]</li>
                                <li>M9A [Alstom]</li>
                            </ul>
                        </li>
                    </ul>

                    <!-- Washington DC Metro -->
                    <div class="collapsible-header text-lg font-medium text-gray-600 mt-2" data-target-content="dc-metro">
                        Washington DC Metro <span class="arrow"></span>
                    </div>
                    <ul id="dc-metro" class="collapsible-content list-disc pl-5 mt-1 space-y-1">
                        <li>
                            <div class="collapsible-header text-md font-normal text-gray-500" data-target-content="dc-rs">
                                Subpage - Rolling Stock <span class="arrow"></span>
                            </div>
                            <ul id="dc-rs" class="collapsible-content list-circle pl-5 mt-1 space-y-0.5 text-sm">
                                <li>1000 Series [Rohr]</li>
                                <li>2000 Series [Breda]</li>
                                <li>3000 Series [Breda]</li>
                                <li>4000 Series [Breda]</li>
                                <li>5000 Series [CAF/AAI]</li>
                                <li>6000 Series [Alstom]</li>
                                <li>7000 Series [Kawasaki]</li>
                            </ul>
                        </li>
                    </ul>

                    <!-- PATH -->
                    <div class="collapsible-header text-lg font-medium text-gray-600 mt-2" data-target-content="path">
                        PATH <span class="arrow"></span>
                    </div>
                    <ul id="path" class="collapsible-content list-disc pl-5 mt-1 space-y-1">
                        <li>
                            <div class="collapsible-header text-md font-normal text-gray-500" data-target-content="path-rs">
                                Subpage - Rolling Stock <span class="arrow"></span>
                            </div>
                            <ul id="path-rs" class="collapsible-content list-circle pl-5 mt-1 space-y-0.5 text-sm">
                                <li>PA1 [St. Louis]</li>
                                <li>PA2 [St. Louis]</li>
                                <li>PA3 [Hawker Siddeley]</li>
                                <li>PA4 [Kawasaki]</li>
                                <li>PA5 [Kawasaki]</li>
                            </ul>
                        </li>
                        <li>
                            <div class="collapsible-header text-md font-normal text-gray-500" data-target-content="path-lines">
                                Subpage - Lines <span class="arrow"></span>
                            </div>
                            <ul id="path-lines" class="collapsible-content list-circle pl-5 mt-1 space-y-0.5 text-sm">
                                <li>Newark–World Trade Center (NWK–WTC)</li>
                                <li>Hoboken–World Trade Center (HOB–WTC)</li>
                                <li>Journal Square–33rd Street (JSQ–33)</li>
                                <li>Hoboken–33rd Street (HOB–33)</li>
                            </ul>
                        </li>
                    </ul>

                    <!-- New Jersey Transit -->
                    <div class="collapsible-header text-lg font-medium text-gray-600 mt-2" data-target-content="njt">
                        New Jersey Transit <span class="arrow"></span>
                    </div>
                    <ul id="njt" class="collapsible-content list-disc pl-5 mt-1 space-y-1">
                        <li>
                            <div class="collapsible-header text-md font-normal text-gray-500" data-target-content="njt-locos">
                                List of Locos <span class="arrow"></span>
                            </div>
                            <ul id="njt-locos" class="collapsible-content list-circle pl-5 mt-1 space-y-0.5 text-sm">
                                <li>ALP-46 [Bombardier]</li>
                                <li>ALP-45DP [Bombardier]</li>
                                <li>GP40PH-2B [EMD]</li>
                                <li>PL42AC [Alstom]</li>
                                <li>F40PH-3C [EMD]</li>
                            </ul>
                        </li>
                        <li>
                            <div class="collapsible-header text-md font-normal text-gray-500" data-target-content="njt-rs">
                                List of Rolling Stock <span class="arrow"></span>
                            </div>
                            <ul id="njt-rs" class="collapsible-content list-circle pl-5 mt-1 space-y-0.5 text-sm">
                                <li>Comet V [Bombardier]</li>
                                <li>MultiLevel Coach [Bombardier]</li>
                                <li>Arrow III [GE]</li>
                                <li>Bombardier Bilevel Coach</li>
                            </ul>
                        </li>
                    </ul>

                    <!-- PATCO -->
                    <div class="collapsible-header text-lg font-medium text-gray-600 mt-2" data-target-content="patco">
                        PATCO <span class="arrow"></span>
                    </div>
                    <ul id="patco" class="collapsible-content list-disc pl-5 mt-1 space-y-1">
                        <li>
                            <div class="collapsible-header text-md font-normal text-gray-500" data-target-content="patco-fleet">
                                Fleet <span class="arrow"></span>
                            </div>
                            <ul id="patco-fleet" class="collapsible-content list-circle pl-5 mt-1 space-y-0.5 text-sm">
                                <li>PATCO IV [Bombardier]</li>
                                <li>PATCO V (future)</li>
                            </ul>
                        </li>
                    </ul>

                    <!-- SEPTA -->
                    <div class="collapsible-header text-lg font-medium text-gray-600 mt-2" data-target-content="septa">
                        SEPTA <span class="arrow"></span>
                    </div>
                    <ul id="septa" class="collapsible-content list-disc pl-5 mt-1 space-y-1">
                        <li>
                            <div class="collapsible-header text-md font-normal text-gray-500" data-target-content="septa-fleet">
                                Fleet <span class="arrow"></span>
                            </div>
                            <ul id="septa-fleet" class="collapsible-content list-circle pl-5 mt-1 space-y-0.5 text-sm">
                                <li>Silverliner IV [Budd]</li>
                                <li>Silverliner V [Hyundai Rotem]</li>
                                <li>Broad Street Line M-4 Cars [Kawasaki]</li>
                                <li>Market–Frankford Line M-3 Cars [Bombardier]</li>
                            </ul>
                        </li>
                    </ul>

                    <!-- AMTRAK -->
                    <div class="collapsible-header text-lg font-medium text-gray-600 mt-2" data-target-content="amtrak">
                        AMTRAK <span class="arrow"></span>
                    </div>
                    <ul id="amtrak" class="collapsible-content list-disc pl-5 mt-1 space-y-1">
                        <li>
                            <div class="collapsible-header text-md font-normal text-gray-500" data-target-content="amtrak-fleet">
                                Fleet <span class="arrow"></span>
                            </div>
                            <ul id="amtrak-fleet" class="collapsible-content list-circle pl-5 mt-1 space-y-0.5 text-sm">
                                <li>ACS-64 [Siemens] (Electric Locomotive)</li>
                                <li>P42DC [GE] (Diesel Locomotive)</li>
                                <li>Acela Express [Alstom/Bombardier]</li>
                                <li>Amfleet I & II Passenger Cars</li>
                                <li>Superliner Passenger Cars</li>
                            </ul>
                        </li>
                    </ul>

                </div>
            </div>
            <!-- End Rolling Stock Section -->

        </div>

        <!-- Links and Resources Page Section -->
        <div id="links" class="page-section text-left">
            <h2 class="text-3xl font-bold text-gray-800 mb-6 pb-2 border-b-2 border-blue-400">Links and Resources</h2>
            <p class="text-gray-600 text-lg">
                This section will contain useful links and resources related to VENY Simulations.
                (Content to be added here)
            </p>
        </div>

    </div>

    <script>
        document.addEventListener('DOMContentLoaded', () => {
            // Function to show/hide page sections
            const showPage = (targetId) => {
                document.querySelectorAll('.page-section').forEach(section => {
                    section.classList.remove('active');
                });
                document.getElementById(targetId).classList.add('active');
            };

            // Event listeners for navigation links
            document.querySelectorAll('.nav-link').forEach(link => {
                link.addEventListener('click', (event) => {
                    showPage(event.target.dataset.target);
                });
            });

            // Function to toggle collapsible content
            const toggleCollapsible = (header) => {
                const targetId = header.dataset.targetContent;
                const content = document.getElementById(targetId);
                if (content) {
                    content.classList.toggle('expanded');
                    header.classList.toggle('expanded'); // Toggle arrow icon
                }
            };

            // Event listeners for collapsible headers
            document.querySelectorAll('.collapsible-header').forEach(header => {
                header.addEventListener('click', () => {
                    toggleCollapsible(header);
                });
            });

            // LLM Feature Implementation
            const generateFactBtn = document.getElementById('generateFactBtn');
            const factDisplay = document.getElementById('factDisplay');
            const loadingIndicator = document.getElementById('loadingIndicator');

            // Function to collect all rolling stock entries from the DOM
            const getAllRollingStock = () => {
                const stockItems = [];
                // Select all list items directly under ul elements within the rolling-stock section
                const lists = document.querySelectorAll('#rolling-stock li');
                lists.forEach(item => {
                    // Get only the direct text content, ignoring nested lists
                    const textContent = item.firstChild ? item.firstChild.textContent.trim() : '';
                    if (textContent && !item.querySelector('ul')) { // Only add if it's a direct item, not a parent of a sub-list
                         stockItems.push(textContent);
                    }
                });
                 // As a fallback and to ensure we capture deeply nested items not just direct LIs of a UL:
                // We can also gather text nodes that are not within other collapsibles or list items directly.
                // This is a bit more complex, but a simpler way is to just target all 'li' elements and filter out the 'collapsible-header'
                document.querySelectorAll('#rolling-stock ul li').forEach(li => {
                    // Check if the li directly contains text and not just another collapsible header
                    const textNodes = Array.from(li.childNodes).filter(node => node.nodeType === Node.TEXT_NODE && node.textContent.trim().length > 0);
                    if (textNodes.length > 0) {
                        const itemText = textNodes.map(node => node.textContent.trim()).join(' ').replace(/[\n\r]+/g, ' ').trim();
                        // Avoid adding duplicates or empty strings
                        if (itemText && !stockItems.includes(itemText) && !itemText.startsWith('Subpage -') && !itemText.startsWith('(Input List')) {
                             stockItems.push(itemText);
                        }
                    }
                });
                return stockItems.filter(item => item !== ''); // Filter out any empty strings
            };


            generateFactBtn.addEventListener('click', async () => {
                factDisplay.textContent = '';
                loadingIndicator.classList.remove('hidden');

                const allRollingStock = getAllRollingStock();
                if (allRollingStock.length === 0) {
                    factDisplay.textContent = 'Could not find any rolling stock items to generate a fact about.';
                    loadingIndicator.classList.add('hidden');
                    return;
                }

                // Randomly pick one rolling stock item
                const randomIndex = Math.floor(Math.random() * allRollingStock.length);
                const selectedRollingStock = allRollingStock[randomIndex];

                try {
                    let chatHistory = [];
                    chatHistory.push({ role: "user", parts: [{ text: `Tell me a single, interesting, fun fact about the "${selectedRollingStock}" train or locomotive. Keep the fact concise and engaging. Do not include introductory phrases like "Here's a fact" or "Did you know?".` }] });
                    const payload = { contents: chatHistory };
                    const apiKey = ""; // Canvas will provide this key
                    const apiUrl = `https://generativelanguage.googleapis.com/v1beta/models/gemini-2.0-flash:generateContent?key=${apiKey}`;

                    const response = await fetch(apiUrl, {
                        method: 'POST',
                        headers: { 'Content-Type': 'application/json' },
                        body: JSON.stringify(payload)
                    });

                    const result = await response.json();
                    if (result.candidates && result.candidates.length > 0 &&
                        result.candidates[0].content && result.candidates[0].content.parts &&
                        result.candidates[0].content.parts.length > 0) {
                        const text = result.candidates[0].content.parts[0].text;
                        factDisplay.textContent = text;
                    } else {
                        factDisplay.textContent = 'Sorry, I could not generate a fact at this time.';
                        console.error('Gemini API response structure unexpected:', result);
                    }
                } catch (error) {
                    factDisplay.textContent = 'Failed to generate a fact. Please try again later.';
                    console.error('Error calling Gemini API:', error);
                } finally {
                    loadingIndicator.classList.add('hidden');
                }
            });

            // Initially show the home page
            showPage('home');
        });
    </script>
</body>
</html>
