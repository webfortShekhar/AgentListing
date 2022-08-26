<template>
    <header class="fixed top-0 left-0 right-0 w-full h-16 z-50">
        <nav class="bg-white border-b dark:border-0 border-gray-200 px-5 py-3 dark:bg-gray-900 h-full">
            <div class="flex flex-wrap justify-between items-center mx-auto w-full">
                <a href="https://flowbite.com" class="flex items-center">
                    <img src="https://flowbite.com/docs/images/logo.svg" class="mr-3 h-6 sm:h-9" alt="Flowbite Logo" />
                    <span class="self-center text-xl font-semibold whitespace-nowrap dark:text-white">Flowbite</span>
                </a>

                <!-- Call Ongoing Panel -->
                <div class="flex justify-between divide-x dark:divide-slate-600 py-0">
                    <div class="flex items-center px-3">
                        <!-- User Image -->
                        <img class="w-10 h-10 rounded-full shadow-sm mr-4"
                            src="https://flowbite.com/docs/images/people/profile-picture-5.jpg" alt="Rounded avatar" />

                        <!-- Mobile Number and Time -->
                        <div class="mr-0">
                            <div class="text-sm md:text-md font-semibold dark:text-white">
                                +91 9999985424
                            </div>
                            <div class="text-sm font-medium text-green-600 dark:text-green-500 text-left">
                                00 : 08
                            </div>
                        </div>
                    </div>
                    <div class="flex items-center px-3">
                        <div class="hidden sm:flex rounded-md mr-4" role="group">
                            <!-- Call Pause -->
                            <button type="button"
                                class="py-2 flex items-center px-3 text-sm font-medium text-gray-900 bg-white rounded hover:bg-gray-100 hover:text-blue-700 focus:z-10 focus:ring-0 focus:ring-blue-700 focus:text-blue-700 dark:bg-transparent dark:text-white dark:hover:text-white dark:hover:bg-gray-600 dark:focus:ring-blue-500 dark:focus:text-white">
                                <span class="material-icons-outlined"> phone_paused </span>
                            </button>

                            <!-- Voice Muted -->
                            <button type="button"
                                class="py-2 flex items-center px-3 text-sm font-medium text-gray-900 bg-white rounded hover:bg-gray-100 hover:text-blue-700 focus:z-10 focus:ring-0 focus:ring-blue-700 focus:text-blue-700 dark:bg-transparent dark:text-white dark:hover:text-white dark:hover:bg-gray-600 dark:focus:ring-blue-500 dark:focus:text-white">
                                <span class="material-icons-outlined"> keyboard_voice </span>
                            </button>

                            <!-- Leave Comments -->
                            <Popover class="relative">
                                <PopoverButton>
                                    <button type="button"
                                        class="py-2 flex items-center px-3 text-sm font-medium text-gray-900 bg-white rounded hover:bg-gray-100 hover:text-blue-700 focus:z-10 focus:ring-0 focus:ring-blue-700 focus:text-blue-700 dark:bg-transparent dark:text-white dark:hover:text-white dark:hover:bg-gray-600 dark:focus:ring-blue-500 dark:focus:text-white">
                                        <span class="material-icons-outlined"> question_answer </span>
                                    </button>
                                </PopoverButton>

                                <PopoverPanel
                                    class="absolute left-1/2 z-30 mt-4 w-screen max-w-sm -translate-x-1/2 transform px-4 sm:px-0 lg:max-w-xl">
                                    <div
                                        class="overflow-hidden rounded-lg shadow-2xl ring-1 bg-white ring-black ring-opacity-5">
                                        <div class="w-full">
                                            <div class="bg-white dark:bg-slate-900 px-3 py-3">
                                                <textarea id="message" rows="4"
                                                    class="block p-2.5 w-full text-sm text-gray-900 bg-transparent rounded-lg border-0 border-gray-300 focus:ring-blue-500 focus:border-blue-500 dark:bg-transparent dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500"
                                                    placeholder="Leave a comment..."></textarea>
                                            </div>
                                            <div class="bg-blue-50 dark:bg-gray-700 p-3 rounded-b-lg flex justify-end">
                                                <button type="button"
                                                    class="text-white flex items-center bg-gradient-to-r from-blue-500 via-blue-600 to-blue-700 hover:bg-gradient-to-br focus:ring-4 focus:outline-none focus:ring-blue-300 dark:focus:ring-blue-800 shadow-lg shadow-blue-500/50 dark:shadow-lg dark:shadow-blue-800/80 font-medium rounded-lg text-sm px-5 py-2.5 text-center">
                                                    <span class="material-icons-outlined mr-2 text-md"> done_all </span>
                                                    Save
                                                </button>
                                            </div>
                                        </div>
                                    </div>
                                </PopoverPanel>
                            </Popover>

                            <!-- Call Forword -->
                            <button type="button"
                                class="py-2 flex items-center px-3 text-sm font-medium text-gray-900 bg-white rounded hover:bg-gray-100 hover:text-blue-700 focus:z-10 focus:ring-0 focus:ring-blue-700 focus:text-blue-700 dark:bg-transparent dark:text-white dark:hover:text-white dark:hover:bg-gray-600 dark:focus:ring-blue-500 dark:focus:text-white">
                                <span class="material-icons-outlined"> phone_forwarded </span>
                            </button>

                            <!-- Add Group -->
                            <Popover class="relative">
                                <PopoverButton>
                                    <button type="button"
                                        class="py-2 flex items-center px-3 text-sm font-medium text-gray-900 bg-white rounded hover:bg-gray-100 hover:text-blue-700 focus:z-10 focus:ring-0 focus:ring-blue-700 focus:text-blue-700 dark:bg-transparent dark:text-white dark:hover:text-white dark:hover:bg-gray-600 dark:focus:ring-blue-500 dark:focus:text-white">
                                        <span class="material-icons-outlined"> group_add </span>
                                    </button>
                                </PopoverButton>

                                <PopoverPanel
                                    class="absolute left-1/2 z-50 mt-4 w-screen max-w-sm -translate-x-1/2 transform px-4 sm:px-0 lg:max-w-xl">
                                    <div
                                        class="overflow-hidden rounded-lg shadow-2xl ring-1 bg-white ring-black ring-opacity-5">
                                        <div class="w-full">
                                            <div
                                                class="bg-white dark:bg-slate-900 px-3 py-3 overflow-auto h-80 scrollbar">
                                                <ul role="list" class="divide-y divide-gray-200 dark:divide-gray-700">
                                                    <li v-for="index in 10" :key="index" class="py-3 sm:py-4">
                                                        <div class="flex items-center space-x-4">
                                                            <div class="flex-shrink-0">
                                                                <img class="w-8 h-8 rounded-full"
                                                                    src="https://flowbite.com/docs/images/people/profile-picture-4.jpg"
                                                                    alt="Neil image">
                                                            </div>
                                                            <div class="flex-1 min-w-0">
                                                                <p
                                                                    class="text-sm font-medium text-gray-900 truncate dark:text-white">
                                                                    Neil Sims
                                                                </p>
                                                                <p
                                                                    class="text-sm text-gray-500 truncate dark:text-gray-400">
                                                                    email@windster.com
                                                                </p>
                                                            </div>
                                                            <div
                                                                class="inline-flex items-center text-base font-semibold text-gray-900 dark:text-white">
                                                                <button type="button"
                                                                    class="text-white bg-green-700 hover:bg-green-800 focus:outline-none focus:ring-4 focus:ring-green-300 font-medium rounded-full text-sm p-2 h-8 w-8 text-center dark:bg-green-600 dark:hover:bg-green-700 dark:focus:ring-green-800 flex justify-center items-center"><span
                                                                        class="material-icons-outlined text-lg">local_phone</span></button>
                                                            </div>
                                                        </div>
                                                    </li>
                                                </ul>
                                            </div>
                                        </div>
                                    </div>
                                </PopoverPanel>
                            </Popover>

                            <!-- Open Dialer -->
                            <button type="button"
                                class="py-2 px-4 flex items-center text-sm font-medium text-gray-900 bg-white rounded hover:bg-gray-100 hover:text-blue-700 focus:z-10 focus:ring-0 focus:ring-blue-700 focus:text-blue-700 dark:bg-transparent dark:text-white dark:hover:text-white dark:hover:bg-gray-600 dark:focus:ring-blue-500 dark:focus:text-white">
                                <span class="material-icons-sharp"> dialpad </span>
                            </button>
                        </div>

                        <button type="button"
                            class="text-white md:ml-6 flex items-center justify-center bg-gradient-to-r from-red-600 via-red-500 to-red-600 hover:bg-gradient-to-br focus:ring-4 focus:outline-none focus:ring-red-300 dark:focus:ring-red-800 shadow-lg shadow-red-500/50 dark:shadow-lg dark:shadow-red-800/80 font-medium rounded-full text-sm h-10 w-10 text-center">
                            <span class="material-icons-outlined"> call_end </span>
                        </button>
                    </div>
                </div>

                <div class="flex item-center w-fit divide-x divide-dotted divide-slate-500 dark:divide-slate-400">
                    <div class="px-3 flex items-center">
                        <Menu>
                            <MenuButton
                                class="inline-flex items-center text-sm font-medium text-center text-gray-500 hover:text-gray-900 focus:outline-none dark:hover:text-white dark:text-gray-400"
                                type="button">
                                <svg class="w-6 h-6" aria-hidden="true" fill="currentColor" viewBox="0 0 20 20"
                                    xmlns="http://www.w3.org/2000/svg">
                                    <path
                                        d="M10 2a6 6 0 00-6 6v3.586l-.707.707A1 1 0 004 14h12a1 1 0 00.707-1.707L16 11.586V8a6 6 0 00-6-6zM10 18a3 3 0 01-3-3h6a3 3 0 01-3 3z">
                                    </path>
                                </svg>
                                <div class="flex relative">
                                    <div
                                        class="inline-flex relative -top-2 right-3 w-3 h-3 bg-red-500 rounded-full border-2 border-white dark:border-gray-900">
                                    </div>
                                </div>
                            </MenuButton>

                            <!-- Dropdown menu -->
                            <transition enter-active-class="transition duration-100 ease-out"
                                enter-from-class="transform scale-95 opacity-0"
                                enter-to-class="transform scale-100 opacity-100"
                                leave-active-class="transition duration-75 ease-in"
                                leave-from-class="transform scale-100 opacity-100"
                                leave-to-class="transform scale-95 opacity-0">
                                <MenuItems
                                    class="absolute mt-3 top-14 right-64 origin-top-right z-20 w-full max-w-sm bg-white divide-y rounded-lg divide-gray-100 drop-shadow-2xl dark:bg-slate-900 dark:divide-gray-700">
                                    <div
                                        class="block py-2 px-4 font-medium rounded-t-lg text-center text-gray-700 bg-gray-200 dark:bg-slate-900 dark:text-white">
                                        Notifications
                                    </div>
                                    <div class="divide-y divide-gray-100 dark:divide-gray-700">
                                        <a href="#" class="flex py-3 px-4 hover:bg-gray-100 dark:hover:bg-gray-700">
                                            <div class="flex-shrink-0">
                                                <img class="w-11 h-11 rounded-full"
                                                    src="https://flowbite.com/docs/images/people/profile-picture-1.jpg"
                                                    alt="Jese image">
                                                <div
                                                    class="flex absolute justify-center items-center ml-6 -mt-5 w-5 h-5 bg-blue-600 rounded-full border border-white dark:border-gray-800">
                                                    <svg class="w-3 h-3 text-white" aria-hidden="true"
                                                        fill="currentColor" viewBox="0 0 20 20"
                                                        xmlns="http://www.w3.org/2000/svg">
                                                        <path
                                                            d="M8.707 7.293a1 1 0 00-1.414 1.414l2 2a1 1 0 001.414 0l2-2a1 1 0 00-1.414-1.414L11 7.586V3a1 1 0 10-2 0v4.586l-.293-.293z">
                                                        </path>
                                                        <path
                                                            d="M3 5a2 2 0 012-2h1a1 1 0 010 2H5v7h2l1 2h4l1-2h2V5h-1a1 1 0 110-2h1a2 2 0 012 2v10a2 2 0 01-2 2H5a2 2 0 01-2-2V5z">
                                                        </path>
                                                    </svg>
                                                </div>
                                            </div>
                                            <div class="pl-3 w-full">
                                                <div class="text-gray-500 text-sm mb-1.5 dark:text-gray-400">New message
                                                    from
                                                    <span class="font-semibold text-gray-900 dark:text-white">Jese
                                                        Leos</span>:
                                                    "Hey, what's up? All set for the presentation?"
                                                </div>
                                                <div class="text-xs text-blue-600 dark:text-blue-500">a few moments ago
                                                </div>
                                            </div>
                                        </a>
                                        <a href="#" class="flex py-3 px-4 hover:bg-gray-100 dark:hover:bg-gray-700">
                                            <div class="flex-shrink-0">
                                                <img class="w-11 h-11 rounded-full"
                                                    src="https://flowbite.com/docs/images/people/profile-picture-2.jpg"
                                                    alt="Joseph image">
                                                <div
                                                    class="flex absolute justify-center items-center ml-6 -mt-5 w-5 h-5 bg-gray-900 rounded-full border border-white dark:border-gray-800">
                                                    <svg class="w-3 h-3 text-white" aria-hidden="true"
                                                        fill="currentColor" viewBox="0 0 20 20"
                                                        xmlns="http://www.w3.org/2000/svg">
                                                        <path
                                                            d="M8 9a3 3 0 100-6 3 3 0 000 6zM8 11a6 6 0 016 6H2a6 6 0 016-6zM16 7a1 1 0 10-2 0v1h-1a1 1 0 100 2h1v1a1 1 0 102 0v-1h1a1 1 0 100-2h-1V7z">
                                                        </path>
                                                    </svg>
                                                </div>
                                            </div>
                                            <div class="pl-3 w-full">
                                                <div class="text-gray-500 text-sm mb-1.5 dark:text-gray-400"><span
                                                        class="font-semibold text-gray-900 dark:text-white">Joseph
                                                        Mcfall</span>
                                                    and <span class="font-medium text-gray-900 dark:text-white">5
                                                        others</span>
                                                    started following you.</div>
                                                <div class="text-xs text-blue-600 dark:text-blue-500">10 minutes ago
                                                </div>
                                            </div>
                                        </a>
                                        <a href="#" class="flex py-3 px-4 hover:bg-gray-100 dark:hover:bg-gray-700">
                                            <div class="flex-shrink-0">
                                                <img class="w-11 h-11 rounded-full"
                                                    src="https://flowbite.com/docs/images/people/profile-picture-3.jpg"
                                                    alt="Bonnie image">
                                                <div
                                                    class="flex absolute justify-center items-center ml-6 -mt-5 w-5 h-5 bg-red-600 rounded-full border border-white dark:border-gray-800">
                                                    <svg class="w-3 h-3 text-white" aria-hidden="true"
                                                        fill="currentColor" viewBox="0 0 20 20"
                                                        xmlns="http://www.w3.org/2000/svg">
                                                        <path fill-rule="evenodd"
                                                            d="M3.172 5.172a4 4 0 015.656 0L10 6.343l1.172-1.171a4 4 0 115.656 5.656L10 17.657l-6.828-6.829a4 4 0 010-5.656z"
                                                            clip-rule="evenodd"></path>
                                                    </svg>
                                                </div>
                                            </div>
                                            <div class="pl-3 w-full">
                                                <div class="text-gray-500 text-sm mb-1.5 dark:text-gray-400"><span
                                                        class="font-semibold text-gray-900 dark:text-white">Bonnie
                                                        Green</span>
                                                    and <span class="font-medium text-gray-900 dark:text-white">141
                                                        others</span> love your story. See it and view more stories.
                                                </div>
                                                <div class="text-xs text-blue-600 dark:text-blue-500">44 minutes ago
                                                </div>
                                            </div>
                                        </a>
                                        <a href="#" class="flex py-3 px-4 hover:bg-gray-100 dark:hover:bg-gray-700">
                                            <div class="flex-shrink-0">
                                                <img class="w-11 h-11 rounded-full"
                                                    src="https://flowbite.com/docs/images/people/profile-picture-4.jpg"
                                                    alt="Leslie image">
                                                <div
                                                    class="flex absolute justify-center items-center ml-6 -mt-5 w-5 h-5 bg-green-400 rounded-full border border-white dark:border-gray-800">
                                                    <svg class="w-3 h-3 text-white" aria-hidden="true"
                                                        fill="currentColor" viewBox="0 0 20 20"
                                                        xmlns="http://www.w3.org/2000/svg">
                                                        <path fill-rule="evenodd"
                                                            d="M18 13V5a2 2 0 00-2-2H4a2 2 0 00-2 2v8a2 2 0 002 2h3l3 3 3-3h3a2 2 0 002-2zM5 7a1 1 0 011-1h8a1 1 0 110 2H6a1 1 0 01-1-1zm1 3a1 1 0 100 2h3a1 1 0 100-2H6z"
                                                            clip-rule="evenodd"></path>
                                                    </svg>
                                                </div>
                                            </div>
                                            <div class="pl-3 w-full">
                                                <div class="text-gray-500 text-sm mb-1.5 dark:text-gray-400"><span
                                                        class="font-semibold text-gray-900 dark:text-white">Leslie
                                                        Livingston</span> mentioned you in a comment: <span
                                                        class="font-medium text-blue-500" href="#">@bonnie.green</span>
                                                    what do
                                                    you say?</div>
                                                <div class="text-xs text-blue-600 dark:text-blue-500">1 hour ago</div>
                                            </div>
                                        </a>
                                        <a href="#" class="flex py-3 px-4 hover:bg-gray-100 dark:hover:bg-gray-700">
                                            <div class="flex-shrink-0">
                                                <img class="w-11 h-11 rounded-full"
                                                    src="https://flowbite.com/docs/images/people/profile-picture-5.jpg"
                                                    alt="Robert image">
                                                <div
                                                    class="flex absolute justify-center items-center ml-6 -mt-5 w-5 h-5 bg-purple-500 rounded-full border border-white dark:border-gray-800">
                                                    <svg class="w-3 h-3 text-white" aria-hidden="true"
                                                        fill="currentColor" viewBox="0 0 20 20"
                                                        xmlns="http://www.w3.org/2000/svg">
                                                        <path
                                                            d="M2 6a2 2 0 012-2h6a2 2 0 012 2v8a2 2 0 01-2 2H4a2 2 0 01-2-2V6zM14.553 7.106A1 1 0 0014 8v4a1 1 0 00.553.894l2 1A1 1 0 0018 13V7a1 1 0 00-1.447-.894l-2 1z">
                                                        </path>
                                                    </svg>
                                                </div>
                                            </div>
                                            <div class="pl-3 w-full">
                                                <div class="text-gray-500 text-sm mb-1.5 dark:text-gray-400"><span
                                                        class="font-semibold text-gray-900 dark:text-white">Robert
                                                        Brown</span>
                                                    posted a new video: Glassmorphism - learn how to implement the new
                                                    design
                                                    trend.</div>
                                                <div class="text-xs text-blue-600 dark:text-blue-500">3 hours ago</div>
                                            </div>
                                        </a>
                                    </div>
                                    <a href="#"
                                        class="block py-2 text-sm font-medium rounded-b-lg text-center text-slate-900 bg-slate-200 hover:bg-slate-300 dark:bg-slate-900 dark:hover:bg-slate-700 dark:text-white">
                                        <div class="inline-flex items-center ">
                                            <svg class="mr-2 w-4 h-4 text-gray-500 dark:text-gray-400"
                                                aria-hidden="true" fill="currentColor" viewBox="0 0 20 20"
                                                xmlns="http://www.w3.org/2000/svg">
                                                <path d="M10 12a2 2 0 100-4 2 2 0 000 4z"></path>
                                                <path fill-rule="evenodd"
                                                    d="M.458 10C1.732 5.943 5.522 3 10 3s8.268 2.943 9.542 7c-1.274 4.057-5.064 7-9.542 7S1.732 14.057.458 10zM14 10a4 4 0 11-8 0 4 4 0 018 0z"
                                                    clip-rule="evenodd"></path>
                                            </svg>
                                            View all
                                        </div>
                                    </a>
                                </MenuItems>
                            </transition>
                        </Menu>
                    </div>
                    <div class="px-3">
                        <Menu>
                            <MenuButton class="flex items-center cursor-pointer space-x-3">
                                <!-- User with Image -->
                                <img class="w-10 h-10 rounded-full"
                                    src="https://flowbite.com/docs/images/people/profile-picture-5.jpg" alt="">
                                <!-- Placeholder initials -->
                                <span class="hidden">
                                    <div
                                        class="inline-flex overflow-hidden relative justify-center items-center w-10 h-10 bg-gray-100 rounded-full dark:bg-gray-600">
                                        <span class="font-medium text-gray-600 dark:text-gray-300">JL</span>
                                    </div>
                                </span>
                                <div class="font-medium dark:text-white flex items-center">
                                    <div class="mr-2">
                                        <div>Vikas Yadav</div>
                                        <div class="text-xs text-gray-500 dark:text-gray-400">Twilio Bal: $52 </div>
                                    </div>
                                    <span class="material-icons-outlined">arrow_drop_down</span>
                                </div>
                            </MenuButton>

                            <!-- Dropdown menu -->
                            <transition enter-active-class="transition duration-100 ease-out"
                                enter-from-class="transform scale-95 opacity-0"
                                enter-to-class="transform scale-100 opacity-100"
                                leave-active-class="transition duration-75 ease-in"
                                leave-from-class="transform scale-100 opacity-100"
                                leave-to-class="transform scale-95 opacity-0">
                                <MenuItems
                                    class="absolute mt-3 top-14 right-20 origin-top-right z-20 w-44 bg-white divide-y rounded-lg divide-gray-100 drop-shadow-2xl dark:bg-slate-900 dark:divide-gray-700">
                                    <div class="py-3 px-4 text-sm text-gray-900 dark:text-white">
                                        <div>Vikas Yadav</div>
                                        <div class="font-medium truncate">webfort.vikasyadav@flowbite.com</div>
                                    </div>
                                    <ul class="py-1 text-sm text-gray-700 dark:text-gray-200"
                                        aria-labelledby="dropdownInformationButton">
                                        <li>
                                            <a href="#"
                                                class="py-1 px-4 hover:bg-gray-100 dark:hover:bg-gray-600 dark:hover:text-white space-x-3 flex items-center">
                                                <span class="material-icons-outlined text-xl"> dashboard </span>
                                                <span>Dashboard</span>
                                            </a>
                                        </li>
                                        <li>
                                            <a href="#"
                                                class="py-1 px-4 hover:bg-gray-100 dark:hover:bg-gray-600 dark:hover:text-white space-x-3 flex items-center">
                                                <span class="material-icons-outlined text-xl"> settings </span>
                                                <span>Settings</span>
                                            </a>
                                        </li>
                                    </ul>
                                    <div class="py-1 text-sm text-gray-700 dark:text-gray-200">
                                        <a href="#"
                                            class="py-1 px-4 hover:bg-gray-100 dark:hover:bg-gray-600 dark:hover:text-white space-x-3 flex items-center">
                                            <span class="material-icons-outlined text-xl"> logout </span>
                                            <span>
                                                Sign out
                                            </span>
                                        </a>
                                    </div>
                                </MenuItems>
                            </transition>
                        </Menu>
                    </div>
                    <div class="px-3">
                        <Menu>
                            <MenuButton type="button"
                                class="flex items-center justify-center text-gray-500 hover:text-white bg-gray-200 hover:bg-gray-900 focus:outline-none focus:ring-0 focus:ring-gray-300 font-medium rounded-lg text-sm px-2 py-2 dark:bg-gray-800 dark:hover:bg-gray-700 dark:focus:ring-gray-700 dark:border-gray-700">
                                <span class="material-icons"> menu </span>
                            </MenuButton>

                            <!-- This `show` prop controls all nested `TransitionChild` components. -->
                            <TransitionRoot>
                                <!-- Background overlay -->
                                <TransitionChild enter="transition-opacity ease-linear duration-300"
                                    enter-from="opacity-0" enter-to="opacity-100"
                                    leave="transition-opacity ease-linear duration-300" leave-from="opacity-100"
                                    leave-to="opacity-0">
                                    <div class="bg-gray-900 bg-opacity-50 dark:bg-opacity-80 fixed inset-0 z-30"></div>
                                </TransitionChild>

                                <!-- Sliding sidebar -->
                                <TransitionChild
                                    class="fixed right-0 top-0 z-40 h-screen origin-top-right p-4 overflow-x-auto bg-white w-80 dark:bg-gray-800 shadow-2xl"
                                    enter="transition ease-in-out duration-300 transform" enter-from="translate-x-full"
                                    enter-to="translate-x-0" leave="transition ease-in-out duration-300 transform"
                                    leave-from="translate-x-0" leave-to="translate-x-full">
                                    <MenuItems>
                                        <h5 id="drawer-navigation-label"
                                            class="text-base font-semibold text-gray-500 uppercase dark:text-gray-400">
                                            Menu</h5>
                                        <MenuButton type="button"
                                            class="text-gray-400 bg-transparent hover:bg-gray-200 hover:text-gray-900 rounded-lg text-sm p-1.5 absolute top-2.5 right-2.5 inline-flex items-center dark:hover:bg-gray-600 dark:hover:text-white">
                                            <svg aria-hidden="true" class="w-5 h-5" fill="currentColor"
                                                viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg">
                                                <path fill-rule="evenodd"
                                                    d="M4.293 4.293a1 1 0 011.414 0L10 8.586l4.293-4.293a1 1 0 111.414 1.414L11.414 10l4.293 4.293a1 1 0 01-1.414 1.414L10 11.414l-4.293 4.293a1 1 0 01-1.414-1.414L8.586 10 4.293 5.707a1 1 0 010-1.414z"
                                                    clip-rule="evenodd"></path>
                                            </svg>
                                            <span class="sr-only">Close menu</span>
                                        </MenuButton>
                                        <div class="py-4 overflow-y-auto">
                                            <ul class="space-y-2">
                                                <li>
                                                    <a href="#"
                                                        class="flex items-center p-2 text-base font-normal text-gray-900 rounded-lg dark:text-white hover:bg-gray-100 dark:hover:bg-gray-700">
                                                        <span class="material-icons-sharp"> dashboard </span>
                                                        <span class="ml-3">Dashboard</span>
                                                    </a>
                                                </li>

                                                <li>
                                                    <a href="#"
                                                        class="flex items-center p-2 text-base font-normal text-gray-900 rounded-lg dark:text-white hover:bg-gray-100 dark:hover:bg-gray-700">
                                                        <span class="material-icons-sharp"> call </span>
                                                        <span class="ml-3">Call Logs</span>
                                                    </a>
                                                </li>

                                                <li>
                                                    <a href="#"
                                                        class="flex items-center p-2 text-base font-normal text-gray-900 rounded-lg dark:text-white hover:bg-gray-100 dark:hover:bg-gray-700">
                                                        <span class="material-icons-sharp"> support_agent </span>
                                                        <span class="ml-3">Agents</span>
                                                    </a>
                                                </li>

                                                <li>
                                                    <a href="#"
                                                        class="flex items-center p-2 text-base font-normal text-gray-900 rounded-lg dark:text-white hover:bg-gray-100 dark:hover:bg-gray-700">
                                                        <span class="material-icons-sharp"> settings </span>
                                                        <span class="ml-3">Settings</span>
                                                    </a>
                                                </li>

                                                <li>
                                                    <a href="#"
                                                        class="flex items-center p-2 text-base font-normal text-gray-900 rounded-lg dark:text-white hover:bg-gray-100 dark:hover:bg-gray-700">
                                                        <span class="material-icons-sharp"> logout </span>
                                                        <span class="ml-3">Logout</span>
                                                    </a>
                                                </li>
                                            </ul>
                                        </div>
                                    </MenuItems>
                                </TransitionChild>
                            </TransitionRoot>
                        </Menu>
                    </div>
                </div>
            </div>
        </nav>
    </header>
</template>

<script>
import { Popover, PopoverButton, PopoverPanel, Menu, MenuButton, MenuItems, MenuItem, TransitionRoot, TransitionChild } from "@headlessui/vue";

export default {
    components: {
        Popover,
        PopoverButton,
        PopoverPanel,
        Menu,
        MenuButton,
        MenuItems,
        MenuItem,
        TransitionRoot,
        TransitionChild
    }
}
</script>
