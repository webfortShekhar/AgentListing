<template>
    <div class="bg-white rounded-0 border-0 dark:bg-gray-800 h-[calc(100vh_-_64px)] p-2">
        <TabGroup>
            <TabList class="flex space-x-1 rounded-xl bg-zinc-900/10 dark:bg-zinc-600/60 p-1">
                <Tab class="w-full flex items-center justify-center rounded-lg p-1 text-sm focus:outline-none ring-0 "
                    :class="{ 'text-blue-50 bg-blue-600/100 shadow': isActive == 'phone' }" type="button"
                    @click="isActive = 'phone'">
                    <span class="material-icons-outlined text-base mr-1"> call </span> Phone
                </Tab>

                <Tab class="w-full flex items-center justify-center rounded-lg p-1 text-sm  dark:text-blue-100 dark:hover:bg-white/[0.12]  dark:hover:text-blue-100 focus:outline-none"
                    type="button" @click="isActive = 'contacts'"
                    :class="{ 'bg-blue-600/100 text-blue-50 shadow': isActive == 'contacts' }">
                    <span class="material-icons-outlined text-base mr-1"> group </span> Contacts
                </Tab>

                <Tab class="w-full flex items-center justify-center rounded-lg p-1 text-sm dark:text-blue-100  dark:hover:bg-white/[0.12]  dark:hover:text-blue-100 focus:outline-none"
                    type="button" @click="isActive = 'favorites'"
                    :class="{ 'bg-blue-600/100 text-blue-50 shadow': isActive == 'favorites' }">
                    <span class="material-icons-outlined text-base mr-1"> book </span> Favorites
                </Tab>
            </TabList>

            <TabPanels>
                <!-- ========================================================= -->
                <!-- Phone Tab Panel -->
                <!-- ========================================================= -->
                <TabPanel>
                    <div class="mt-1 p-0 rounded-t-xl bg-zinc-900/10 dark:dark:bg-zinc-600/60 pr-1 pb-2">
                        <div class="text-xs p-1 flex justify-between items-center text-gray-500 dark:text-gray-400">
                            <!-- Search -->
                            <div class="mr-2 flex-1">
                                <label for="default-search"
                                    class="mb-2 text-sm font-medium text-gray-900 sr-only dark:text-gray-300">Search
                                </label>
                                <div class="relative">
                                    <div class="flex absolute inset-y-0 left-0 items-center pl-2 pointer-events-none">
                                        <svg aria-hidden="true" class="w-5 h-5 text-gray-500 dark:text-gray-400"
                                            fill="none" stroke="currentColor" viewBox="0 0 24 24"
                                            xmlns="http://www.w3.org/2000/svg">
                                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                                                d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z"></path>
                                        </svg>
                                    </div>
                                    <input type="search" id="default-search"
                                        class="block p-1 pl-9 w-full text-sm text-gray-900 bg-gray-50 rounded-lg border-0 border-gray-300 focus:ring-blue-500 focus:border-blue-500 dark:bg-gray-800 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500"
                                        placeholder="Search" required="">
                                </div>
                            </div>

                            <!-- Filter -->
                            <div class="flex items-center">
                                <div class="relative">
                                    <Menu>
                                        <MenuButton
                                            class="inline-flex items-center text-sm font-medium text-center text-gray-500 hover:text-gray-900 focus:outline-none dark:hover:text-white dark:text-gray-400"
                                            type="button">
                                            <span class="material-icons-outlined"> filter_list </span>
                                        </MenuButton>

                                        <!-- Dropdown menu -->
                                        <transition enter-active-class="transition duration-100 ease-out"
                                            enter-from-class="transform scale-95 opacity-0"
                                            enter-to-class="transform scale-100 opacity-100"
                                            leave-active-class="transition duration-75 ease-in"
                                            leave-from-class="transform scale-100 opacity-100"
                                            leave-to-class="transform scale-95 opacity-0">
                                            <MenuItems
                                                class="absolute top-8 right-2 rounded-xl z-50 w-48 bg-white px-3 pt-4 pb-1 shadow-xl dark:bg-zinc-800 dark:divide-gray-600">
                                                <div class="ml-3 text-sm font-medium text-gray-900 dark:text-gray-300">
                                                    Filter calls</div>
                                                <ul class="p-3 space-y-3 text-sm text-gray-700 dark:text-gray-200">
                                                    <li>
                                                        <div class="flex items-center">
                                                            <input id="default-radio-1" v-model="filter_calls"
                                                                type="radio" value="" name="default-radio"
                                                                class="w-4 h-4 text-blue-600 bg-gray-100 border-gray-300 focus:ring-blue-500 dark:focus:ring-blue-600 dark:ring-offset-gray-700 focus:ring-2 dark:bg-gray-600 dark:border-gray-500">
                                                            <label for="default-radio-1"
                                                                class="ml-2 text-sm font-medium text-gray-900 dark:text-gray-300">All
                                                                Calls</label>
                                                        </div>
                                                    </li>
                                                    <li>
                                                        <div class="flex items-center">
                                                            <input checked id="default-radio-2" type="radio" value="Missed
                                                        calls" name="default-radio"
                                                                class="w-4 h-4 text-blue-600 bg-gray-100 border-gray-300 focus:ring-blue-500 dark:focus:ring-blue-600 dark:ring-offset-gray-700 focus:ring-2 dark:bg-gray-600 dark:border-gray-500">
                                                            <label for="default-radio-2"
                                                                class="ml-2 text-sm font-medium text-gray-900 dark:text-gray-300">Missed
                                                                calls</label>
                                                        </div>
                                                    </li>
                                                    <li>
                                                        <div class="flex items-center">
                                                            <input id="default-radio-3" type="radio" value="Rejected
                                                        calls" name="default-radio"
                                                                class="w-4 h-4 text-blue-600 bg-gray-100 border-gray-300 focus:ring-blue-500 dark:focus:ring-blue-600 dark:ring-offset-gray-700 focus:ring-2 dark:bg-gray-600 dark:border-gray-500">
                                                            <label for="default-radio-3"
                                                                class="ml-2 text-sm font-medium text-gray-900 dark:text-gray-300">Rejected
                                                                calls</label>
                                                        </div>
                                                    </li>
                                                    <li>
                                                        <div class="flex items-center">
                                                            <input id="default-radio-4" type="radio" value="Outgoing
                                                        calls" name="default-radio"
                                                                class="w-4 h-4 text-blue-600 bg-gray-100 border-gray-300 focus:ring-blue-500 dark:focus:ring-blue-600 dark:ring-offset-gray-700 focus:ring-2 dark:bg-gray-600 dark:border-gray-500">
                                                            <label for="default-radio-4"
                                                                class="ml-2 text-sm font-medium text-gray-900 dark:text-gray-300">Outgoing
                                                                calls</label>
                                                        </div>
                                                    </li>
                                                    <li>
                                                        <div class="flex items-center">
                                                            <input id="default-radio-5" type="radio" value="Incoming
                                                        calls" name="default-radio"
                                                                class="w-4 h-4 text-blue-600 bg-gray-100 border-gray-300 focus:ring-blue-500 dark:focus:ring-blue-600 dark:ring-offset-gray-700 focus:ring-2 dark:bg-gray-600 dark:border-gray-500">
                                                            <label for="default-radio-5"
                                                                class="ml-2 text-sm font-medium text-gray-900 dark:text-gray-300">Incoming
                                                                calls</label>
                                                        </div>
                                                    </li>
                                                </ul>
                                            </MenuItems>
                                        </transition>
                                    </Menu>
                                </div>
                            </div>
                        </div>

                        <div class="h-[calc(100vh_-_490px)] 2xl:h-[calc(100vh_-_490px)] w-full overflow-auto scrollbar">
                            <div class="text-xs px-2 py-1 text-gray-500 truncate dark:text-gray-400">
                                Today
                            </div>

                            <ul role="list" class="divide-y divide-gray-50 dark:divide-gray-600 px-2">
                                <li class="px-0 py-2 cursor-pointer">
                                    <div class="flex items-center space-x-2">
                                        <div class="flex-shrink-0">
                                            <img class="w-7 h-7 rounded-full"
                                                src="https://flowbite.com/docs/images/people/profile-picture-4.jpg"
                                                alt="Neil image">
                                        </div>
                                        <div class="flex-1 min-w-0">
                                            <p
                                                class="text-xs font-medium flex items-center text-gray-900 truncate dark:text-white">
                                                Neil Sims <span
                                                    class="material-icons-outlined ml-2 text-base text-red-600">
                                                    call_missed
                                                </span>
                                            </p>
                                            <p class="text-xs text-gray-500 truncate dark:text-gray-400">
                                                +91-999900000
                                            </p>
                                        </div>
                                        <div
                                            class="inline-flex items-center text-base font-semibold text-gray-900 dark:text-white">
                                            <p class="text-xs text-gray-500 truncate dark:text-gray-400">
                                                18:30
                                            </p>
                                        </div>
                                    </div>
                                </li>
                                <li class="px-0 py-2 cursor-pointer">
                                    <div class="flex items-center space-x-2">
                                        <div class="flex-shrink-0">
                                            <img class="w-7 h-7 rounded-full"
                                                src="https://flowbite.com/docs/images/people/profile-picture-4.jpg"
                                                alt="Neil image">
                                        </div>
                                        <div class="flex-1 min-w-0">
                                            <p
                                                class="text-xs font-medium flex items-center text-gray-900 truncate dark:text-white">
                                                Neil Sims <span
                                                    class="material-icons-outlined ml-2 text-base text-green-600">
                                                    call_received
                                                </span>
                                            </p>
                                            <p class="text-xs text-gray-500 truncate dark:text-gray-400">
                                                +91-999900000
                                            </p>
                                        </div>
                                        <div
                                            class="inline-flex items-center text-base font-semibold text-gray-900 dark:text-white">
                                            <p class="text-xs text-gray-500 truncate dark:text-gray-400">
                                                18:30
                                            </p>
                                        </div>
                                    </div>
                                </li>
                                <li class="px-0 py-2 cursor-pointer">
                                    <div class="flex items-center space-x-2">
                                        <div class="flex-shrink-0">
                                            <img class="w-7 h-7 rounded-full"
                                                src="https://flowbite.com/docs/images/people/profile-picture-4.jpg"
                                                alt="Neil image">
                                        </div>
                                        <div class="flex-1 min-w-0">
                                            <p
                                                class="text-xs font-medium flex items-center text-gray-900 truncate dark:text-white">
                                                Neil Sims <span
                                                    class="material-icons-outlined ml-2 text-base text-yellow-600">
                                                    call_made
                                                </span>
                                            </p>
                                            <p class="text-xs text-gray-500 truncate dark:text-gray-400">
                                                +91-999900000
                                            </p>
                                        </div>
                                        <div
                                            class="inline-flex items-center text-base font-semibold text-gray-900 dark:text-white">
                                            <p class="text-xs text-gray-500 truncate dark:text-gray-400">
                                                18:30
                                            </p>
                                        </div>
                                    </div>
                                </li>
                                <li class="px-0 py-2 cursor-pointer">
                                    <div class="flex items-center space-x-2">
                                        <div class="flex-shrink-0">
                                            <img class="w-7 h-7 rounded-full"
                                                src="https://flowbite.com/docs/images/people/profile-picture-4.jpg"
                                                alt="Neil image">
                                        </div>
                                        <div class="flex-1 min-w-0">
                                            <p
                                                class="text-xs font-medium flex items-center text-gray-900 truncate dark:text-white">
                                                Neil Sims <span
                                                    class="material-icons-outlined ml-2 text-base text-green-600">
                                                    call_received
                                                </span>
                                            </p>
                                            <p class="text-xs text-gray-500 truncate dark:text-gray-400">
                                                +91-999900000
                                            </p>
                                        </div>
                                        <div
                                            class="inline-flex items-center text-base font-semibold text-gray-900 dark:text-white">
                                            <p class="text-xs text-gray-500 truncate dark:text-gray-400">
                                                18:30
                                            </p>
                                        </div>
                                    </div>
                                </li>
                            </ul>
                        </div>
                    </div>
                </TabPanel>

                <!-- ========================================================= -->
                <!-- Contacts Tab Panel -->
                <!-- ========================================================= -->
                <TabPanel>
                    <div class="mt-1 p-0 rounded-t-xl bg-zinc-900/10 dark:dark:bg-zinc-600/60 pr-1 pb-2">
                        <div
                            class="text-xs p-1 flex justify-between items-center text-gray-500 truncate dark:text-gray-400">
                            <!-- Search -->
                            <div class="flex-1">
                                <label for="default-search"
                                    class="mb-2 text-sm font-medium text-gray-900 sr-only dark:text-gray-300">Search
                                </label>
                                <div class="relative">
                                    <div class="flex absolute inset-y-0 left-0 items-center pl-2 pointer-events-none">
                                        <svg aria-hidden="true" class="w-5 h-5 text-gray-500 dark:text-gray-400"
                                            fill="none" stroke="currentColor" viewBox="0 0 24 24"
                                            xmlns="http://www.w3.org/2000/svg">
                                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                                                d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z"></path>
                                        </svg>
                                    </div>
                                    <input type="search" id="default-search" v-model="contact_query"
                                        class="block p-1 pl-9 w-full text-sm text-gray-900 bg-gray-50 rounded-lg border-0 border-gray-300 focus:ring-blue-500 focus:border-blue-500 dark:bg-gray-800 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500"
                                        placeholder="Search Contacts" required="" @keyup="load_contacts">
                                </div>
                            </div>
                        </div>

                        <div class="h-[calc(100vh_-_490px)] 2xl:h-[calc(100vh_-_490px)] w-full overflow-auto scrollbar">
                            <ul role="list" class="divide-y divide-gray-50 dark:divide-gray-600 px-2">
                                <!-- <Skeleton v-if="contact.length"></Skeleton> -->
                                <template v-if="contact.contact_list.length" v-for="items in contact.contact_list"
                                    :key="items">
                                    <li class="px-0 py-2 cursor-pointer">
                                        <div class="flex items-center space-x-2">
                                            <div class="flex-shrink-0">
                                                <img class="w-7 h-7 rounded-full"
                                                    src="https://flowbite.com/docs/images/people/profile-picture-4.jpg"
                                                    alt="Neil image">
                                            </div>
                                            <div class="flex-1 min-w-0">
                                                <p
                                                    class="text-xs font-medium flex items-center text-gray-900 truncate dark:text-white">
                                                    {{ items.contact_name }}
                                                </p>
                                                <p class="text-xs text-gray-500 truncate dark:text-gray-400">
                                                    {{ items.phone }}
                                                </p>
                                            </div>
                                            <div @click="to_phone = items.phone"
                                                class="inline-flex items-center text-base font-semibold text-gray-900 dark:text-white">
                                                <p class="text-xs text-gray-500 truncate dark:text-gray-400">
                                                    <span class="material-icons text-lg"> phone_enabled </span>
                                                </p>
                                            </div>
                                        </div>
                                    </li>
                                </template>
                                <template v-else>
                                    <h3 class="ml-4"> No Recordings Available</h3>
                                </template>
                            </ul>
                        </div>
                    </div>
                </TabPanel>

                <!-- ========================================================= -->
                <!-- Favorites Tab Panel -->
                <!-- ========================================================= -->
                <TabPanel>
                    <div class="mt-1 p-0 rounded-t-xl bg-zinc-900/10 dark:dark:bg-zinc-600/60 pr-1 pb-2">
                        <div
                            class="text-xs p-1 flex justify-between items-center text-gray-500 truncate dark:text-gray-400">
                            <!-- Search -->
                            <div class="flex-1">
                                <label for="default-search"
                                    class="mb-2 text-sm font-medium text-gray-900 sr-only dark:text-gray-300">Search
                                </label>
                                <div class="relative">
                                    <div class="flex absolute inset-y-0 left-0 items-center pl-2 pointer-events-none">
                                        <svg aria-hidden="true" class="w-5 h-5 text-gray-500 dark:text-gray-400"
                                            fill="none" stroke="currentColor" viewBox="0 0 24 24"
                                            xmlns="http://www.w3.org/2000/svg">
                                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                                                d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z"></path>
                                        </svg>
                                    </div>
                                    <input type="search " id="default-search"
                                        class="block p-1 pl-9 w-full text-sm text-gray-900 bg-gray-50 rounded-lg border-0 border-gray-300 focus:ring-blue-500 focus:border-blue-500 dark:bg-gray-800 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500"
                                        placeholder="Search Favorites" required="">
                                </div>
                            </div>
                        </div>

                        <div class="h-[calc(100vh_-_490px)] 2xl:h-[calc(100vh_-_490px)] w-full overflow-auto scrollbar">
                            <ul role="list" class="divide-y divide-gray-50 dark:divide-gray-600 px-2">
                                <li class="px-0 py-2 cursor-pointer" v-for="index in 20" :key="index">
                                    <div class="flex items-center space-x-2">
                                        <div class="flex-shrink-0">
                                            <img class="w-7 h-7 rounded-full"
                                                src="https://flowbite.com/docs/images/people/profile-picture-4.jpg"
                                                alt="Neil image">
                                        </div>
                                        <div class="flex-1 min-w-0">
                                            <p
                                                class="text-xs font-medium flex items-center text-gray-900 truncate dark:text-white">
                                                Neil Sims
                                            </p>
                                            <p class="text-xs text-gray-500 truncate dark:text-gray-400">
                                                +91-999900000
                                            </p>
                                        </div>
                                        <div
                                            class="inline-flex items-center text-base font-semibold text-gray-900 dark:text-white">
                                            <p class="text-xs text-gray-500 truncate dark:text-gray-400">
                                                <span class="material-icons text-lg"> phone_enabled </span>
                                            </p>
                                        </div>
                                    </div>
                                </li>
                            </ul>
                        </div>
                    </div>
                </TabPanel>
            </TabPanels>
        </TabGroup>

        <aside class="">
            <!-- =============================================================== -->
            <!-- User Details -->
            <!-- =============================================================== -->
            <div
                class="sm:grid sm:grid-cols-5 md:grid-cols-1 sm:gap-5 md:gap-0 bg-zinc-900/10 dark:dark:bg-zinc-600/60 rounded-b-xl pb-3">
                <div class="col-span-3 md:col-span-full">
                    <!-- =============================================================== -->
                    <!-- Display -->
                    <!-- =============================================================== -->
                    <div>
                        <label for="search"
                            class="mb-2 text-sm font-medium text-gray-900 sr-only dark:text-gray-300">Your Email</label>
                        <div class="relative">
                            <input type="search" id="search"
                                class="block px-4 py-3 w-full text-sm text-white border-0 rounded-0 focus:ring-blue-500 bg-zinc-500 dark:bg-slate-900 placeholder-gray-50 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500"
                                placeholder="Phone Number" required="" v-model="to_phone" :maxlength="maxLength">
                        </div>
                    </div>
                </div>
                <!-- =============================================================== -->
                <!-- Dialer -->
                <!-- =============================================================== -->
                <div class="col-span-2 px-0 md:col-span-full w-full text-center mt-4">
                    <div class="px-3">
                        <div class="grid grid-cols-3 gap-2">
                            <button type="button" @click="dial(1), playSound(1)"
                                class="text-gray-900 flex items-start justify-center bg-transparent hover:bg-gray-300 focus:outline-none focus:ring-0 focus:ring-gray-300 font-medium rounded-full text-sm px-5 py-1 dark:hover:bg-gray-800 dark:focus:ring-gray-700 dark:text-white dark:border-gray-700">
                                <div>1</div>
                            </button>

                            <button type="button" @click="dial(2), playSound(2)"
                                class="text-gray-900 bg-transparent hover:bg-gray-300 focus:outline-none focus:ring-0 focus:ring-gray-300 font-medium rounded-full text-sm px-5 py-1 dark:hover:bg-gray-800 dark:focus:ring-gray-700 dark:text-white dark:border-gray-700">
                                <div>2</div>
                                <div class="text-xs text-gray-500 dark:text-gray-400">ABC</div>
                            </button>

                            <button type="button" @click="dial(3), playSound(3)"
                                class="text-gray-900 bg-transparent hover:bg-gray-300 focus:outline-none focus:ring-0 focus:ring-gray-300 font-medium rounded-full text-sm px-5 py-1 dark:hover:bg-gray-800 dark:focus:ring-gray-700 dark:text-white dark:border-gray-700">
                                <div>3</div>
                                <div class="text-xs text-gray-500 dark:text-gray-400">DEF</div>
                            </button>

                            <button type="button" @click="dial(4), playSound(4)"
                                class="text-gray-900 bg-transparent hover:bg-gray-300 focus:outline-none focus:ring-0 focus:ring-gray-300 font-medium rounded-full text-sm px-5 py-1 dark:hover:bg-gray-800 dark:focus:ring-gray-700 dark:text-white dark:border-gray-700">
                                <div>4</div>
                                <div class="text-xs text-gray-500 dark:text-gray-400">GHI</div>
                            </button>

                            <button type="button" @click="dial(5), playSound(5)"
                                class="text-gray-900 bg-transparent hover:bg-gray-300 focus:outline-none focus:ring-0 focus:ring-gray-300 font-medium rounded-full text-sm px-5 py-1 dark:hover:bg-gray-800 dark:focus:ring-gray-700 dark:text-white dark:border-gray-700">
                                <div>5</div>
                                <div class="text-xs text-gray-500 dark:text-gray-400">JKL</div>
                            </button>

                            <button type="button" @click="dial(6), playSound(6)"
                                class="text-gray-900 bg-transparent hover:bg-gray-300 focus:outline-none focus:ring-0 focus:ring-gray-300 font-medium rounded-full text-sm px-5 py-1 dark:hover:bg-gray-800 dark:focus:ring-gray-700 dark:text-white dark:border-gray-700">
                                <div>6</div>
                                <div class="text-xs text-gray-500 dark:text-gray-400">MNO</div>
                            </button>

                            <button type="button" @click="dial(7), playSound(7)"
                                class="text-gray-900 bg-transparent hover:bg-gray-300 focus:outline-none focus:ring-0 focus:ring-gray-300 font-medium rounded-full text-sm px-5 py-1 dark:hover:bg-gray-800 dark:focus:ring-gray-700 dark:text-white dark:border-gray-700">
                                <div>7</div>
                                <div class="text-xs text-gray-500 dark:text-gray-400">PQRS</div>
                            </button>

                            <button type="button" @click="dial(8), playSound(8)"
                                class="text-gray-900 bg-transparent hover:bg-gray-300 focus:outline-none focus:ring-0 focus:ring-gray-300 font-medium rounded-full text-sm px-5 py-1 dark:hover:bg-gray-800 dark:focus:ring-gray-700 dark:text-white dark:border-gray-700">
                                <div>8</div>
                                <div class="text-xs text-gray-500 dark:text-gray-400">TUV</div>
                            </button>

                            <button type="button" @click="dial(9), playSound(9)"
                                class="text-gray-900 bg-transparent hover:bg-gray-300 focus:outline-none focus:ring-0 focus:ring-gray-300 font-medium rounded-full text-sm px-5 py-1 dark:hover:bg-gray-800 dark:focus:ring-gray-700 dark:text-white dark:border-gray-700">
                                <div>9</div>
                                <div class="text-xs text-gray-500 dark:text-gray-400">WXYZ</div>
                            </button>

                            <button type="button" @click="dial('*'), playSound('star')"
                                class="text-gray-900 bg-transparent hover:bg-gray-300 focus:outline-none focus:ring-0 focus:ring-gray-300 font-medium rounded-full text-sm px-5 py-1 dark:hover:bg-gray-800 dark:focus:ring-gray-700 dark:text-white dark:border-gray-700">
                                <div>*</div>
                            </button>

                            <button type="button" @click="dial(0), playSound(0)"
                                class="text-gray-900 bg-transparent hover:bg-gray-300 focus:outline-none focus:ring-0 focus:ring-gray-300 font-medium rounded-full text-sm px-5 py-1 dark:hover:bg-gray-800 dark:focus:ring-gray-700 dark:text-white dark:border-gray-700">
                                <div>0</div>
                                <div class="text-xs text-gray-500 dark:text-gray-400">+</div>
                            </button>

                            <button type="button" @click="dial('#'), playSound('hash')"
                                class="text-gray-900 bg-transparent hover:bg-gray-300 focus:outline-none focus:ring-0 focus:ring-gray-300 font-medium rounded-full text-sm px-5 py-1 dark:hover:bg-gray-800 dark:focus:ring-gray-700 dark:text-white dark:border-gray-700">
                                <div>#</div>
                            </button>

                            <button type="button"
                                class="col-start-2 text-white flex items-center justify-center bg-green-600 hover:bg-green-800 focus:outline-none focus:ring-4 focus:ring-green-300 font-medium rounded-full text-sm px-5 py-2.5 text-centerdark:bg-green-600 dark:hover:bg-green-700 dark:focus:ring-green-800">
                                <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20" fill="currentColor"
                                    aria-hidden="true" class="h-5 w-5">
                                    <path
                                        d="M2 3a1 1 0 011-1h2.153a1 1 0 01.986.836l.74 4.435a1 1 0 01-.54 1.06l-1.548.773a11.037 11.037 0 006.105 6.105l.774-1.548a1 1 0 011.059-.54l4.435.74a1 1 0 01.836.986V17a1 1 0 01-1 1h-2C7.82 18 2 12.18 2 5V3z">
                                    </path>
                                </svg>
                            </button>

                            <button type="button"
                                class="text-gray-900 flex items-center justify-center bg-transparent hover:bg-gray-300 focus:outline-none focus:ring-0 focus:ring-gray-300 font-medium rounded-full text-sm px-5 py-0 dark:hover:bg-gray-800 dark:focus:ring-gray-700 dark:text-white dark:border-gray-700">
                                <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20" fill="currentColor"
                                    aria-hidden="true" class="h-5 w-5">
                                    <path fill-rule="evenodd"
                                        d="M6.707 4.879A3 3 0 018.828 4H15a3 3 0 013 3v6a3 3 0 01-3 3H8.828a3 3 0 01-2.12-.879l-4.415-4.414a1 1 0 010-1.414l4.414-4.414zm4 2.414a1 1 0 00-1.414 1.414L10.586 10l-1.293 1.293a1 1 0 101.414 1.414L12 11.414l1.293 1.293a1 1 0 001.414-1.414L13.414 10l1.293-1.293a1 1 0 00-1.414-1.414L12 8.586l-1.293-1.293z"
                                        clip-rule="evenodd"></path>
                                </svg>
                            </button>
                        </div>
                    </div>
                </div>
            </div>
        </aside>

        <!-- Notification -->
        <div class="invisible fixed bottom-3 items-center p-4 w-full max-w-xs text-gray-400  bg-gray-800 rounded-lg shadow dark:text-gray-600 dark:bg-white"
            role="alert">
            <div
                class="inline-flex flex-shrink-0 justify-center items-center w-8 h-8 text-orange-500 bg-orange-100 rounded-lg dark:bg-orange-700 dark:text-orange-200">
                <svg aria-hidden="true" class="w-5 h-5" fill="currentColor" viewBox="0 0 20 20"
                    xmlns="http://www.w3.org/2000/svg">
                    <path fill-rule="evenodd"
                        d="M8.257 3.099c.765-1.36 2.722-1.36 3.486 0l5.58 9.92c.75 1.334-.213 2.98-1.742 2.98H4.42c-1.53 0-2.493-1.646-1.743-2.98l5.58-9.92zM11 13a1 1 0 11-2 0 1 1 0 012 0zm-1-8a1 1 0 00-1 1v3a1 1 0 002 0V6a1 1 0 00-1-1z"
                        clip-rule="evenodd"></path>
                </svg>
                <span class="sr-only">Warning icon</span>
            </div>
            <div class="ml-3 text-sm font-normal">Improve password difficulty.</div>
            <button type="button"
                class="ml-auto -mx-1.5 -my-1.5 bg-gray-800 text-gray-500 hover:text-white rounded-lg focus:ring-0 focus:ring-gray-300 p-1.5 hover:bg-gray-700 inline-flex h-8 w-8 dark:text-gray-400 dark:hover:text-gray-900 dark:bg-white dark:hover:bg-gray-100"
                data-dismiss-target="#toast-warning" aria-label="Close">
                <span class="sr-only">Close</span>
                <svg aria-hidden="true" class="w-5 h-5" fill="currentColor" viewBox="0 0 20 20"
                    xmlns="http://www.w3.org/2000/svg">
                    <path fill-rule="evenodd"
                        d="M4.293 4.293a1 1 0 011.414 0L10 8.586l4.293-4.293a1 1 0 111.414 1.414L11.414 10l4.293 4.293a1 1 0 01-1.414 1.414L10 11.414l-4.293 4.293a1 1 0 01-1.414-1.414L8.586 10 4.293 5.707a1 1 0 010-1.414z"
                        clip-rule="evenodd"></path>
                </svg>
            </button>
        </div>

    </div>

</template>

<script>
import { Menu, MenuButton, MenuItems, MenuItem, TabGroup, TabList, Tab, TabPanels, TabPanel } from '@headlessui/vue'
import axios from 'axios'
import _ from 'lodash'
import Skeleton from './Skeleton.vue'

export default {
    components: {
        Menu, MenuButton, MenuItems, MenuItem, TabGroup, TabList, Tab, TabPanels, TabPanel, Skeleton
    },
    data() {
        return {
            filter_calls: "",
            contact: [],
            isActive: "phone",
            contact_query: '',
            errorMessage: '',
            to_phone: '+1',
            maxLength: 15,
        }
    },
    async mounted() {
        this.load_contacts()
    },
    methods: {
        load_contacts: _.debounce(function () {

            axios.get('http://localhost/Php_Database_callCenter/contacts.php', { params: { contact_query: this.contact_query }})
                .then(response => {

                    this.contact = response.data
                })
                .catch(function (error) {
                    // handle error

                });
        }, 500),

        playSound(sound) {
            let button = `https://sdk.twilio.com/js/client/sounds/releases/1.0.0/dtmf-${sound}.mp3?cache=2.1.1`
            if (button) {
                var audio = new Audio(button);
                // audio.muted = true;
                audio.play();
            }
        },
        dial(number) {
            this.errorMessage = ""
            this.to_phone += number
        },
        myFilter() {
            this.isActive = !this.isActive;
            // some code to filter users
        },
    },
}
</script>