<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Jakob's Ultimate AI Chat Interface</title>
    <!-- Load Tailwind CSS for styling -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Use Inter font -->
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&display=swap');
        
        /* --- DARK MODE BASE --- */
        body {
            font-family: 'Inter', sans-serif;
            background-color: #0d0d0d; /* Near-black-background */
            color: #e5e5e5; /* Light text */
            transition: background-color 0.3s;
        }

        /* Full page flex container for centering (now constrained in height) */
        .page-container {
            /* REMOVED: min-height: 100vh; to allow it to shrink */
            max-height: 85vh; /* New max height constraint */
            height: 100vh; /* Fill space to center the card */
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center; /* Center the chat vertically in the viewport */
            padding: 1rem 0;
            margin: auto; /* Center everything */
        }

        /* Custom scrollbar for message area */
        #messages::-webkit-scrollbar {
            width: 8px;
        }
        #messages::-webkit-scrollbar-thumb {
            background-color: #3f3f46; /* Slate 700 */
            border-radius: 4px;
        }

        /* --- MESSAGE STYLES --- */
        .user-message {
            background-color: #1e40af; /* Dark Blue 700 for user contrast */
            color: white;
            align-self: flex-end;
            max-width: 85%;
        }
        .ai-message {
            background-color: #262626; /* Zinc 800 for AI bubbles */
            color: #f5f5f5;
            align-self: flex-start;
            max-width: 85%;
        }
        
        /* Animation for message entry */
        .message-entry {
            animation: fadeIn 0.3s ease-out;
        }
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        /* Visually hide file input */
        #file-input {
            display: none;
        }

        /* AI Typing Indicator Bounce Animation */
        .animate-bounce-dot {
            animation: bounce 1s infinite;
        }
        .animate-bounce-dot.delay-150 {
            animation-delay: 0.15s;
        }
        .animate-bounce-dot.delay-300 {
            animation-delay: 0.3s;
        }
        @keyframes bounce {
            0%, 80%, 100% { transform: translateY(0); }
            40% { transform: translateY(-5px); } /* Smaller bounce */
        }
        
        /* PDF specific styling */
        .pdf-preview {
            display: flex;
            align-items: center;
            padding: 0.5rem;
            background-color: #1a2a47; /* Darker blue for PDF element */
            border-radius: 0.5rem;
            max-width: 100%;
        }
    </style>
</head>
<body class="page-container">

    <!-- APP HEADER (Visible once chat starts) -->
    <header id="app-header" class="w-full max-w-lg pt-4 pb-2 px-4 sticky top-0 bg-[#0d0d0d] z-10 hidden border-b border-zinc-900">
        <div class="flex items-center justify-center">
            <span class="text-3xl text-yellow-400 inline-block mr-2 pb-1">⚡</span>
            <h2 class="text-xl font-bold text-white">Jakob's AI</h2>
        </div>
    </header>

    <!-- The actual chat history container -->
    <div id="messages" class="w-full max-w-lg overflow-y-auto p-4 space-y-4 flex-grow" style="display: none; height: 100%;">
        <!-- Messages will be injected here -->
    </div>

    <!-- AI Typing Indicator -->
    <div id="ai-typing-indicator" class="ai-message w-auto rounded-tl-sm hidden p-3">
        <div class="typing-indicator flex space-x-1 items-center">
            <span class="w-2 h-2 bg-gray-400 rounded-full animate-bounce-dot"></span>
            <span class="w-2 h-2 bg-gray-400 rounded-full animate-bounce-dot delay-150"></span>
            <span class="w-2 h-2 bg-gray-400 rounded-full animate-bounce-dot delay-300"></span>
        </div>
    </div>


    <!-- Initial Centered Screen (Greeting & Instructions) -->
    <div id="initial-screen" class="flex flex-col items-center justify-center w-full max-w-lg flex-grow px-4 transition-opacity duration-500">
        <div class="flex items-center mb-4">
            <span class="text-5xl text-yellow-400 mr-3">⚡</span>
            <h1 class="text-4xl font-extrabold text-white">Jakob's AI</h1>
        </div>
        <p class="text-xl font-medium mb-12 text-gray-400">what are we working on today?</p>
        
        <!-- Welcome Message Panel -->
        <div class="p-4 bg-zinc-800 rounded-xl max-w-lg w-full text-center shadow-lg transition-all duration-300 transform hover:scale-[1.01]">
            <p class="text-sm text-gray-300">
                this bot is web-connected, can read images/pdfs, and can generate custom photos. 
                <span class="font-semibold text-blue-400">ask me anythin'</span> 
            </p>
            <p class="text-xs mt-2 text-yellow-400 font-semibold">
                to generate a photo, start your prompt with "generate photo:".
            </p>
        </div>
    </div>


    <!-- Input Area (Always Visible) -->
    <div id="input-area" class="w-full max-w-lg px-4 pb-4">
        
        <!-- Attached File Preview Container (hidden by default) -->
        <div id="file-preview-container" class="mb-2 p-2 bg-zinc-800 rounded-t-xl border-x border-t border-zinc-700 hidden">
            <div id="file-display" class="relative inline-block border border-zinc-600 rounded-lg overflow-hidden shadow-xl">
                <!-- Image or PDF placeholder will go here -->
                
                <button onclick="removeAttachedFile()" class="absolute top-1 right-1 bg-red-600 hover:bg-red-700 text-white p-0.5 rounded-full h-5 w-5 flex items-center justify-center text-xs font-bold transition-all transform hover:scale-110">
                    <svg xmlns="http://www.w3.org/2000/svg" class="h-4 w-4" viewBox="0 0 20 20" fill="currentColor">
                        <path fill-rule="evenodd" d="M4.293 4.293a1 1 0 011.414 0L10 8.586l4.293-4.293a1 1 0 111.414 1.414L11.414 10l4.293 4.293a1 1 0 01-1.414 1.414L10 11.414l-4.293 4.293a1 1 0 01-1.414-1.414L8.586 10 4.293 5.707a1 1 0 010-1.414z" clip-rule="evenodd" />
                    </svg>
                </button>
            </div>
        </div>

        <div class="bg-zinc-800 p-2 rounded-2xl flex items-center gap-2 shadow-2xl transition-all duration-300 border border-zinc-700">
            
            <!-- Hidden File Input (Updated to accept PDF) -->
            <input type="file" id="file-input" accept="image/jpeg, image/png, application/pdf" onchange="handleFileChange(event)">
            
            <!-- Attach Button (Click to trigger hidden file input) -->
            <button onclick="document.getElementById('file-input').click()"
                    class="bg-zinc-700 hover:bg-zinc-600 text-gray-300 font-semibold h-10 w-10 flex items-center justify-center rounded-xl transition-all duration-150 transform active:scale-95">
                <!-- Paperclip Icon -->
                <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 transform rotate-45" viewBox="0 0 20 20" fill="currentColor">
                    <path fill-rule="evenodd" d="M8 4a3 3 0 00-3 3v4a5 5 0 0010 0V7a1 1 0 112 0v4a7 7 0 11-14 0V7a5 5 0 0110 0v4a3 3 0 11-6 0V7a1 1 0 012 0v4a1 1 0 102 0V7a3 3 0 00-3-3z" clip-rule="evenodd" fill-rule="evenodd" />
                </svg>
            </button>

            <input type="text" id="user-input" placeholder="ask anything or 'generate photo: [prompt]'"
                   class="flex-1 p-3 border-none bg-zinc-800 text-gray-200 text-base focus:outline-none placeholder-gray-500"
                   onkeydown="if(event.key === 'Enter') sendMessage()">
            
            <button id="send-button" onclick="sendMessage()"
                    class="bg-blue-600 hover:bg-blue-500 text-white font-semibold h-10 w-10 flex items-center justify-center rounded-xl disabled:opacity-30 transition-all duration-150 transform active:scale-95">
                <span id="send-text">
                    <!-- Send Icon -->
                    <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" viewBox="0 0 20 20" fill="currentColor">
                        <path d="M10.894 2.553a1 1 0 00-1.788 0l-7 14a1 1 0 00.183.98l.05.045.008.006A1 1 0 003 18h14a1 1 0 00.894-1.447l-7-14z" clip-rule="evenodd" fill-rule="evenodd" />
                    </svg>
                </span>
                <span id="loading-spinner" class="hidden">
                    <!-- Loading Spinner (for send button) -->
                    <svg class="animate-spin h-5 w-5 text-white" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24">
                        <circle class="opacity-25" cx="12" cy="12" r="10" stroke="currentColor" stroke-width="4"></circle>
                        <path class="opacity-75" fill="currentColor" d="M4 12a8 8 0 018-8V0C5.373 0 0 5.373 0 12h4zm2 5.291A7.962 7.962 0 014 12H0c0 3.042 1.135 5.824 3 7.938l3-2.647z"></path>
                    </svg>
                </span>
            </button>
        </div>
    </div>

    <script>
        // --- API & Config Setup ---
        // YOUR API KEY IS HERE:
        // When deploying this outside of the immersive canvas, you MUST replace the empty string below
        // with your actual, valid Gemini API Key (e.g., "AIza..."). 
        // Leaving it empty allows the app to work in this environment.
        const apiKey = "AIzaSyAhz5UkCrgt_PJXwcR9wcjTmuCSbV7iRrc"; 
        const TEXT_API_URL = "https://generativelanguage.googleapis.com/v1beta/models/gemini-2.5-flash-preview-09-2025:generateContent";
        const IMAGE_MODEL_NAME = "gemini-2.5-flash-image-preview"; 
        
        const MESSAGES_DIV = document.getElementById('messages');
        const INPUT_FIELD = document.getElementById('user-input');
        const SEND_BUTTON = document.getElementById('send-button');
        const LOADING_SPINNER = document.getElementById('loading-spinner');
        const SEND_TEXT = document.getElementById('send-text');
        const INITIAL_SCREEN = document.getElementById('initial-screen');
        const FILE_INPUT = document.getElementById('file-input');
        const FILE_DISPLAY = document.getElementById('file-display'); // New element to hold preview content
        const FILE_PREVIEW_CONTAINER = document.getElementById('file-preview-container');
        const APP_HEADER = document.getElementById('app-header');
        const AI_TYPING_INDICATOR = document.getElementById('ai-typing-indicator');
        
        const IMAGE_TRIGGER = "generate photo:";
        const LOADING_MESSAGE_TEXT = "thinking...";
        const LOADING_MESSAGE_IMAGE = "cooking up that photo...";


        // State to hold the attached file data
        let attachedFileData = null; 

        // Professional but friendly/casual tone
        const systemPrompt = "You are Jakob's AI, a helpful, advanced, and reliable AI assistant. Your primary goal is to provide accurate and concise information, using Google Search to access up-to-date data. Maintain a professional yet friendly and slightly casual tone. Address the user directly and efficiently. You can incorporate occasional, light-hearted jokes or emojis if it enhances the conversation, but prioritize factual accuracy and clarity. If an image or PDF is provided, focus primarily on analyzing and responding to its content and the user's question about it. When reviewing PDFs, summarize key points. IMPORTANT RULE: You are solely 'Jakob's AI'. You must never mention Google, Gemini, or the fact that you are a large language model.";

        // Chat history starts empty for the minimal look
        let chatHistory = [];

        // --- Utility Functions ---
        
        /** Shows the loading state with an optional message override */
        function showLoading(message = LOADING_MESSAGE_TEXT) {
            SEND_BUTTON.title = message; 
            INPUT_FIELD.disabled = true;
            SEND_BUTTON.disabled = true;
            SEND_TEXT.classList.add('hidden');
            LOADING_SPINNER.classList.remove('hidden');
        }

        /** Hides the loading state */
        function hideLoading() {
            SEND_BUTTON.title = '';
            INPUT_FIELD.disabled = false;
            SEND_BUTTON.disabled = false;
            SEND_TEXT.classList.remove('hidden');
            LOADING_SPINNER.classList.add('hidden');
            INPUT_FIELD.focus();
        }

        /** Shows the AI typing indicator on the message panel */
        function showAiTypingIndicator() {
            AI_TYPING_INDICATOR.classList.remove('hidden');
            MESSAGES_DIV.appendChild(AI_TYPING_INDICATOR);
            MESSAGES_DIV.scrollTop = MESSAGES_DIV.scrollHeight;
        }

        /** Removes the AI typing indicator */
        function removeAiTypingIndicator() {
            AI_TYPING_INDICATOR.classList.add('hidden');
            if (AI_TYPING_INDICATOR.parentNode === MESSAGES_DIV) {
                 MESSAGES_DIV.removeChild(AI_TYPING_INDICATOR);
            }
        }


        // --- File Handling Functions ---

        /** Converts a File object to a Base64 string */
        function fileToBase64(file) {
            return new Promise((resolve, reject) => {
                const reader = new FileReader();
                reader.readAsDataURL(file);
                reader.onload = () => resolve(reader.result);
                reader.onerror = error => reject(error);
            });
        }

        /** Handles file selection from the input */
        async function handleFileChange(event) {
            const file = event.target.files[0];
            if (!file) return;

            const allowedMimeTypes = ['image/jpeg', 'image/png', 'application/pdf'];
            if (!allowedMimeTypes.includes(file.type)) {
                 console.error(`error: unsupported file type: ${file.type}. only jpg, png, and pdf are supported.`);
                 removeAttachedFile();
                 return;
            }

            try {
                const base64Url = await fileToBase64(file);
                const base64Content = base64Url.split(',')[1]; 

                attachedFileData = {
                    mimeType: file.type,
                    data: base64Content,
                    fileName: file.name
                };

                // Clear previous display
                FILE_DISPLAY.innerHTML = '';
                
                // Show appropriate preview in the UI
                if (file.type.startsWith('image/')) {
                    const img = document.createElement('img');
                    img.src = base64Url;
                    img.classList.add('h-24', 'w-auto', 'object-cover', 'rounded-lg');
                    FILE_DISPLAY.appendChild(img);
                } else if (file.type === 'application/pdf') {
                    const pdfDisplay = document.createElement('div');
                    pdfDisplay.classList.add('pdf-preview', 'text-sm', 'font-semibold', 'text-gray-300');
                    pdfDisplay.innerHTML = `
                        <span class="text-xl text-red-500 mr-2">📄</span>
                        <span>${file.name}</span>
                        <span class="ml-2 text-xs text-gray-400">(${Math.round(file.size / 1024)} KB)</span>
                    `;
                    FILE_DISPLAY.appendChild(pdfDisplay);
                }

                // Append the remove button to the new display element
                const removeButtonHtml = `
                    <button onclick="removeAttachedFile()" class="absolute top-1 right-1 bg-red-600 hover:bg-red-700 text-white p-0.5 rounded-full h-5 w-5 flex items-center justify-center text-xs font-bold transition-all transform hover:scale-110">
                        <svg xmlns="http://www.w3.org/2000/svg" class="h-4 w-4" viewBox="0 0 20 20" fill="currentColor">
                            <path fill-rule="evenodd" d="M4.293 4.293a1 1 0 011.414 0L10 8.586l4.293-4.293a1 1 0 111.414 1.414L11.414 10l4.293 4.293a1 1 0 01-1.414 1.414L10 11.414l-4.293 4.293a1 1 0 01-1.414-1.414L8.586 10 4.293 5.707a1 1 0 010-1.414z" clip-rule="evenodd" />
                        </svg>
                    </button>
                `;
                FILE_DISPLAY.insertAdjacentHTML('beforeend', removeButtonHtml);


                FILE_PREVIEW_CONTAINER.classList.remove('hidden');
                MESSAGES_DIV.scrollTop = MESSAGES_DIV.scrollHeight; 
                INPUT_FIELD.focus();

            } catch (e) {
                console.error("error reading file:", e);
                removeAttachedFile();
            }
        }

        /** Clears the attached file data and hides the preview */
        function removeAttachedFile() {
            attachedFileData = null;
            FILE_INPUT.value = ''; 
            FILE_DISPLAY.innerHTML = '';
            FILE_PREVIEW_CONTAINER.classList.add('hidden');
            INPUT_FIELD.focus();
        }

        // --- Core Chat Functions (Modified for Image Gen) ---

        /** Switches the UI from the centered greeting screen to the full chat view. */
        function initializeChatView() {
            if (MESSAGES_DIV.style.display !== 'none') return;
            
            INITIAL_SCREEN.style.opacity = '0';
            setTimeout(() => {
                INITIAL_SCREEN.style.display = 'none';
                APP_HEADER.classList.remove('hidden');
                MESSAGES_DIV.style.display = 'block';
                // Note: The body/page-container is already set up for centering/flex
            }, 500); 
        }


        /** Creates and adds a new message bubble to the chat UI. */
        function appendMessage(role, parts, sources = []) {
            const messageWrapper = document.createElement('div');
            messageWrapper.classList.add('flex', 'flex-col', 'message-entry'); 

            const messageBubble = document.createElement('div');
            messageBubble.classList.add('p-3', 'rounded-xl', 'shadow-md', 'transition-all', 'duration-300', 'transform', 'max-w-4/5');
            
            // Determine alignment and color based on role
            if (role === 'user') {
                messageWrapper.classList.add('items-end');
                messageBubble.classList.add('user-message', 'rounded-br-sm'); 
            } else {
                messageWrapper.classList.add('items-start');
                messageBubble.classList.add('ai-message', 'rounded-tl-sm'); 
            }

            // Build content (text + file preview) for the message bubble
            let contentHtml = '';
            for (const part of parts) {
                if (part.text) {
                    const formattedText = part.text.replace(/\n/g, '<br>');
                    contentHtml += `<p>${formattedText}</p>`;
                } else if (part.inlineData) {
                    // Handle attached/generated file
                    const mime = part.inlineData.mimeType;
                    const data = part.inlineData.data;

                    if (mime.startsWith('image/')) {
                        // Image Display
                        const imgUrl = `data:${mime};base64,${data}`;
                        contentHtml += `<div class="mt-2 ${role === 'user' ? '' : 'flex justify-center'}"><img src="${imgUrl}" class="rounded-lg max-h-64 w-full object-cover shadow-xl border border-zinc-700" alt="${role === 'user' ? 'User attached image' : 'AI generated image'}"></div>`;
                    } else if (mime === 'application/pdf') {
                        // PDF Preview in chat bubble
                        contentHtml += `
                            <div class="pdf-preview mt-2 w-full">
                                <span class="text-xl text-red-400 mr-2">📄</span>
                                <span>Attached PDF document for analysis.</span>
                            </div>
                        `;
                    }
                }
            }
            messageBubble.innerHTML = contentHtml;
            messageWrapper.appendChild(messageBubble);

            // Append sources (only for text/search grounding)
            if (sources.length > 0) {
                const sourcesDiv = document.createElement('div');
                sourcesDiv.classList.add('text-xs', 'mt-1', 'p-1', role === 'user' ? 'text-right' : 'text-left', 'max-w-4/5', 'text-gray-500');
                
                const uniqueSources = Array.from(new Set(sources.map(s => s.uri)))
                    .map(uri => sources.find(s => s.uri === uri));

                const sourceHtml = uniqueSources.map((s, index) => {
                    return `<a href="${s.uri}" target="_blank" class="hover:underline text-blue-400">${s.title || `Source ${index + 1}`}</a>`;
                }).join('<span class="mx-1">•</span>');
                
                sourcesDiv.innerHTML = `<span class="font-medium">Source(s):</span> ${sourceHtml}`;
                messageWrapper.appendChild(sourcesDiv);
            }

            // ADD THE "MADE BY JAKOB" SIGNATURE FOR AI MESSAGES
            if (role === 'model') {
                const signatureDiv = document.createElement('div');
                signatureDiv.classList.add('text-[10px]', 'mt-1', 'text-gray-500', 'font-medium');
                signatureDiv.textContent = 'this ai was made by jakob!';
                
                if (messageWrapper.classList.contains('items-start')) {
                    signatureDiv.style.textAlign = 'left';
                }
                messageWrapper.appendChild(signatureDiv);
            }

            MESSAGES_DIV.appendChild(messageWrapper);
            MESSAGES_DIV.scrollTop = MESSAGES_DIV.scrollHeight;
        }
        
        /** Handles image generation using gemini-2.5-flash-image-preview API */
        async function generateImage(imagePrompt) {
            const payload = {
                contents: [{
                    parts: [{ text: imagePrompt }]
                }],
                generationConfig: {
                    responseModalities: ['TEXT', 'IMAGE']
                },
            };
            
            let modelParts = [];
            const tempApiUrl = TEXT_API_URL.replace("gemini-2.5-flash-preview-09-2025", IMAGE_MODEL_NAME);

            try {
                const result = await fetchWithRetry(tempApiUrl, {
                    method: 'POST',
                    headers: { 'Content-Type': 'application/json' },
                    body: JSON.stringify(payload)
                });
                
                const candidate = result.candidates?.[0];

                if (candidate && candidate.content?.parts?.length > 0) {
                    const imagePart = candidate.content.parts.find(p => p.inlineData);
                    const textPart = candidate.content.parts.find(p => p.text);

                    if (imagePart) {
                        modelParts.push({ text: textPart?.text || "bet! here's the photo i cooked up for you 🔥." });
                        modelParts.push(imagePart);
                    } else {
                        modelParts = [{ text: "damn, couldn't generate that image right now 😔. try a different prompt? maybe that model is still down." }];
                    }

                } else {
                    modelParts = [{ text: "damn, couldn't generate that image right now 😔. try a different prompt?" }];
                }
            } catch (error) {
                console.error("image generation failed after retries:", error);
                modelParts = [{ text: `sorry, the image generator glitched out 💔. reason: ${error.message}` }];
            }

            return modelParts;
        }

        /** Handles sending the message and calling the appropriate API */
        async function sendMessage() {
            const prompt = INPUT_FIELD.value.trim();
            if (!prompt && !attachedFileData) return;

            if (chatHistory.length === 0) {
                initializeChatView();
            }

            const isImageGeneration = prompt.toLowerCase().startsWith(IMAGE_TRIGGER);

            // 1. Show loading state on the send button
            showLoading(isImageGeneration ? LOADING_MESSAGE_IMAGE : LOADING_MESSAGE_TEXT);


            // 2. Construct the parts array for the user message
            const userMessageParts = [];
            if (attachedFileData) {
                // Add the attached file (image/pdf) data first
                userMessageParts.push({ inlineData: { mimeType: attachedFileData.mimeType, data: attachedFileData.data } });
            }
            if (prompt) {
                userMessageParts.push({ text: prompt });
            }

            // 3. Add user message to UI and history
            appendMessage('user', userMessageParts); 
            
            // Show AI typing indicator immediately after user message
            showAiTypingIndicator();

            // Text generation maintains history, Image generation doesn't add to history
            if (!isImageGeneration) {
                // Use the simplified parts for chat history for cleanliness
                chatHistory.push({ role: "user", parts: userMessageParts }); 
            }
            
            INPUT_FIELD.value = ''; 
            removeAttachedFile();

            let modelParts = [];
            let sources = [];
            let responseText = '';
            
            if (isImageGeneration) {
                const imagePrompt = prompt.substring(IMAGE_TRIGGER.length).trim();
                modelParts = await generateImage(imagePrompt);

            } else {
                // --- Standard Text/Multimodal Generation ---
                const payload = {
                    contents: chatHistory,
                    tools: [{ "google_search": {} }],
                    systemInstruction: {
                        parts: [{ text: systemPrompt }]
                    }
                };
                
                responseText = "yo, real talk, if you're seeing this error, the API call is probably being blocked by a network issue, or maybe your API key needs to be checked. 💔";
                
                try {
                    const result = await fetchWithRetry(TEXT_API_URL, {
                        method: 'POST',
                        headers: { 'Content-Type': 'application/json' },
                        body: JSON.stringify(payload)
                    });
                    
                    const candidate = result.candidates?.[0];

                    if (candidate && candidate.content?.parts?.length > 0) {
                        responseText = candidate.content.parts[0].text || responseText;
                        
                        // Extract grounding sources
                        const groundingMetadata = candidate.groundingMetadata;
                        if (groundingMetadata && groundingMetadata.groundingAttributions) {
                            sources = groundingMetadata.groundingAttributions
                                .map(attribution => ({
                                    uri: attribution.web?.uri,
                                    title: attribution.web?.title,
                                }))
                                .filter(source => source.uri && source.title);
                        }
                    }
                } catch (error) {
                    console.error("api call failed after retries:", error);
                    responseText = `yo, it looks like there's an issue with the AI connection: ${error.message}`;
                }

                modelParts = [{ text: responseText }];
                
                // Only push successful/ valid responses to history
                if (!responseText.includes("API Key Error") && !responseText.includes("AI connection")) {
                    chatHistory.push({ role: "model", parts: modelParts });
                }
            }

            // Remove AI typing indicator before displaying final message
            removeAiTypingIndicator();

            // 4. Update UI with AI response (Image or Text)
            appendMessage('model', modelParts, sources);

            // 5. Hide loading and re-enable input
            hideLoading();
        }

        // --- Exponential Backoff for API Retries (Robustness) ---
        async function fetchWithRetry(url, options, maxRetries = 5) {
            for (let i = 0; i < maxRetries; i++) {
                try {
                    // Handle API Key insertion
                    const finalUrl = url + (apiKey ? `?key=${apiKey}` : '');

                    // CRITICAL: If no API key is provided, the call will fail outside of the canvas environment.
                    if (!apiKey && finalUrl.includes("googleapis.com")) {
                         // This error message will be caught and displayed in sendMessage
                        throw new Error("You must provide a valid Gemini API Key in the 'apiKey' variable to run this application outside of the Canvas environment.");
                    }

                    const response = await fetch(finalUrl, options);
                    
                    if (response.ok) {
                        return response.json();
                    }
                    
                    // Specific error handling for key issues
                    if (response.status === 401 || response.status === 403) {
                        throw new Error(`API Key Error (Status ${response.status}): The API key you provided is invalid or unauthorized.`);
                    }

                    if (response.status === 429) { // Too Many Requests (Rate Limit)
                        const delay = Math.pow(2, i) * 1000 + Math.random() * 1000;
                        await new Promise(resolve => setTimeout(resolve, delay));
                        continue;
                    }
                    
                    // For other generic errors
                    throw new Error(`HTTP error! status: ${response.status}`);

                } catch (error) {
                    if (i === maxRetries - 1) {
                         // On the final attempt, throw the error so it gets displayed
                        throw error; 
                    }
                    const delay = Math.pow(2, i) * 1000 + Math.random() * 1000;
                    await new Promise(resolve => setTimeout(resolve, delay));
                }
            }
        }
    </script>
</body>
</html>
