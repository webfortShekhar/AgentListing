<template>
    <TabGroup>
        <div class="border-gray-200 dark:border-gray-700">
            <TabList class="flex flex-wrap -mb-px text-sm font-medium text-center text-gray-500 dark:text-gray-400">
                <Tab type="button" @click="activeTab = 'ongoing'"
                    :class="{ 'text-blue-600 border-blue-600 border-b-2 dark:text-blue-500 dark:border-blue-500': activeTab == 'ongoing' }"
                    class="focus:outline-none mr-2 flex items-center p-4 rounded-t-lg " aria-current="page">
                    <span class="material-icons-outlined">local_phone</span>
                    <div class="mx-2">Ongoing</div>
                    <span
                        class="bg-blue-100 text-blue-800 text-xs font-semibold mr-2 px-1 py-0 rounded dark:bg-blue-200 dark:text-blue-800">{{
                                ongoingCount
                        }}</span>
                </Tab>
                <Tab type="button" @click="activeTab = 'ringing'"
                    :class="{ 'text-blue-600 border-b-2 border-blue-600  dark:text-blue-500 dark:border-blue-500': activeTab == 'ringing' }"
                    class="focus:outline-none mr-2 flex items-center p-4 rounded-t-lg  hover:text-gray-600 hover:border-gray-300 dark:hover:text-gray-300 group">
                    <span class="material-icons-outlined">ring_volume</span>
                    <div class="mx-2">Ringing</div>
                    <span
                        class="bg-blue-100 text-blue-800 text-xs font-semibold mr-2 px-1 py-0 rounded dark:bg-blue-200 dark:text-blue-800">{{
                                ringingCount
                        }}</span>
                </Tab>
                <Tab type="button" @click="activeTab = 'completed'"
                    :class="{ 'text-blue-600 border-b-2 border-blue-600  dark:text-blue-500 dark:border-blue-500': activeTab == 'completed' }"
                    class="focus:outline-none mr-2 flex items-center p-4 rounded-t-lg  hover:text-gray-600 hover:border-gray-300 dark:hover:text-gray-300 group">
                    <span class="material-icons-outlined">call_end</span>
                    <div class="mx-2">Completed</div>
                    <span
                        class="bg-blue-100 text-blue-800 text-xs font-semibold mr-2 px-1 py-0 rounded dark:bg-blue-200 dark:text-blue-800">{{
                                completedCount
                        }}</span>
                </Tab>

            </TabList>
        </div>

        <div class="my-3 pr-3.5">
            <label for="default-search"
                class="mb-2 text-sm font-medium text-gray-900 sr-only dark:text-gray-300">Search</label>
            <div class="relative">
                <div class="flex absolute inset-y-0 left-0 items-center pl-3 pointer-events-none">
                    <svg aria-hidden="true" class="w-5 h-5 text-gray-500 dark:text-gray-400" fill="none"
                        stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                            d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z"></path>
                    </svg>
                </div>
                <input type="search" id="default-search"
                    class="block p-2 pl-10 w-full text-sm text-gray-900 bg-gray-50 rounded-lg border border-gray-300 focus:ring-blue-500 focus:border-blue-500 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500"
                    placeholder="Search online agent..." required="">

            </div>
        </div>
        <TabPanels class="w-full pt-0 overflow-auto h-[calc(100vh_-_194px)] scrollbar pr-3 mb-3">
            <!-- ongoing Tabls -->
            <TabPanel class="grid grid-cols-1 gap-4">
                <Disclosure>
                <Skeleton v-if="people.ongoing.length"></Skeleton>
                <template v-if="people.ongoing.length" v-for="{ items, index } in people.ongoing" :key="index"> 
                    <div
                        class="w-full bg-white rounded-lg border border-gray-200 shadow-md dark:bg-gray-800 dark:border-gray-700">
                        <div class="w-full flex justify-between items-center px-4 py-3">
                            <div class="flex">
                                <div class="flex items-center space-x-3">
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
                                    <div class="font-medium dark:text-white">
                                        <div v-show="items.agent_name == null">unknown </div>
                                        <div>{{ items.agent_name }}</div>
                                        <div class="text-xs text-gray-500 dark:text-gray-400">{{ items.call_time }}
                                        </div>
                                    </div>
                                </div>
                            </div>

                            <div class="flex space-x-2 items-center font-normal text-sm dark:text-white">
                                <span class="material-icons-outlined text-xl">person</span>
                                <div class="space-y-0 text-xs">
                                    <div class="font-semibold">{{ items.contact_name }}</div>
                                    <div>{{ items.From }}</div>
                                </div>
                            </div>

                            <div class="flex space-x-2 items-center font-normal text-sm dark:text-white">
                                <span class="material-icons-outlined text-xl">timer</span>
                                <span>00:06:13</span>
                            </div>

                            <button type="button"
                                class="invisible1 text-white bg-green-700 hover:bg-green-800 focus:outline-none focus:ring-4 focus:ring-green-300 font-medium rounded-full text-sm p-2 h-8 w-8 text-center dark:bg-green-600 dark:hover:bg-green-700 dark:focus:ring-green-800 flex justify-center items-center"><span
                                    class="material-icons-outlined text-lg">local_phone</span></button>

                            <div class="flex space-x-2 items-center">
                                <button type="button"
                                    class="hover:text-white dark:text-white bg-transparent hover:bg-gray-400 focus:outline-none focus:ring-0 focus:ring-gray-300 font-medium rounded-full text-sm px-1 py-1 dark:bg-gray-800 dark:hover:bg-gray-700 dark:focus:ring-gray-700 dark:border-gray-700 flex justify-center items-center">
                                    <span class="material-icons-outlined">more_vert</span>
                                </button>
                                <DisclosureButton type="button"
                                    class="hover:text-white dark:text-white bg-transparent hover:bg-gray-400 focus:outline-none focus:ring-0 focus:ring-gray-300 font-medium rounded-full text-sm px-1 py-1 dark:bg-gray-800 dark:hover:bg-gray-700 dark:focus:ring-gray-700 dark:border-gray-700 flex justify-center items-center">
                                    <span class="material-icons-outlined">arrow_drop_down</span>
                                </DisclosureButton>
                            </div>
                        </div>

                        <!-- Open Content -->
                        <DisclosurePanel
                            class="py-2 px-4 bg-slate-100 dark:bg-slate-700 w-full rounded-b-lg max-h-72 overflow-auto scrollbar">
                            <div class="flex item-center w-full space-x-3 divide-x dark:divide-slate-500 mb-3">

                                <div class="text-xs text-gray-500 dark:text-gray-400 flex items-center space-x-1">
                                    <div class="flex items-center space-x-1">
                                        <span class="material-icons-outlined text-lg">support_agent</span>
                                        <span class="font-bold">Agent Team:</span>
                                    </div>
                                    <span>{{ items.team_name }}</span>
                                </div>

                                <div class="text-xs text-gray-500 dark:text-gray-400 flex items-center space-x-1 pl-2">
                                    <div class="flex items-center space-x-1">
                                        <span class="material-icons-outlined text-lg">topic</span>
                                        <span class="font-bold">Interaction Topic:</span>
                                    </div>
                                    <span>Internet package upgrade</span>
                                </div>
                            </div>
<!-- 
                            <div class="flex items-center space-x-3">
                                <div class="text-base font-bold text-gray-500 dark:text-gray-400 mb-3">Call
                                    Recording:
                                </div>
                                <audio controls>
                                    <source :src="(items.recordings)" type="audio/ogg">
                                </audio>
                            </div> -->


                            <div class="text-sm text-gray-500 dark:text-gray-400">
                                <!-- <p class="mb-2">Dear John Bravo</p> -->

                                <p>{{ items.CallNotes }}</p>
                            </div>


                            <ol class="relative border-l border-gray-200 dark:border-gray-700 mt-10 ml-5 mb-5">
                                <li class="mb-10 ml-6">
                                    <span
                                        class="flex absolute -left-3 justify-center items-center w-6 h-6 bg-blue-200 rounded-full ring-8 ring-slate-100 dark:ring-slate-700 dark:bg-blue-900">
                                        <img class="rounded-full shadow-lg"
                                            src="https://flowbite.com/docs/images/people/profile-picture-3.jpg"
                                            alt="Bonnie image">
                                    </span>
                                    <div
                                        class="justify-between items-center p-4 bg-white rounded-lg border border-gray-200 shadow-sm sm:flex dark:bg-gray-700 dark:border-gray-600">
                                        <time class="mb-1 text-xs font-normal text-gray-400 sm:order-last sm:mb-0">just
                                            now</time>
                                        <div class="text-sm font-normal text-gray-500 dark:text-gray-300">Bonnie
                                            moved
                                            <a href="#"
                                                class="font-semibold text-blue-600 dark:text-blue-500 hover:underline">Jese
                                                Leos</a> to <span
                                                class="bg-gray-100 text-gray-800 text-xs font-normal mr-2 px-2.5 py-0.5 rounded dark:bg-gray-600 dark:text-gray-300">Funny
                                                Group</span>
                                        </div>
                                    </div>
                                </li>
                                <li class="mb-10 ml-6">
                                    <span
                                        class="flex absolute -left-3 justify-center items-center w-6 h-6 bg-blue-200 rounded-full ring-8 ring-slate-100 dark:ring-slate-700 dark:bg-blue-900">
                                        <img class="rounded-full shadow-lg"
                                            src="https://flowbite.com/docs/images/people/profile-picture-5.jpg"
                                            alt="Thomas Lean image">
                                    </span>
                                    <div
                                        class="p-4 bg-white rounded-lg border border-gray-200 shadow-sm dark:bg-gray-700 dark:border-gray-600">
                                        <div class="justify-between items-center mb-3 sm:flex">
                                            <time class="mb-1 text-xs font-normal text-gray-400 sm:order-last sm:mb-0">2
                                                hours ago</time>
                                            <div class="text-sm font-normal text-gray-500 lex dark:text-gray-300">
                                                Thomas
                                                Lean commented on <a href="#"
                                                    class="font-semibold text-gray-900 dark:text-white hover:underline">Flowbite
                                                    Pro</a></div>
                                        </div>
                                        <div
                                            class="p-3 text-xs italic font-normal text-gray-500 bg-gray-50 rounded-lg border border-gray-200 dark:bg-gray-600 dark:border-gray-500 dark:text-gray-300">
                                            Hi ya'll! I wanted to share a webinar zeroheight is having regarding how
                                            to
                                            best
                                            measure your design system! This is the second session of our new
                                            webinar
                                            series
                                            on #DesignSystems discussions where we'll be speaking about Measurement.
                                        </div>
                                    </div>
                                </li>
                                <li class="ml-6">
                                    <span
                                        class="flex absolute -left-3 justify-center items-center w-6 h-6 bg-blue-200 rounded-full ring-8 ring-slate-100 dark:ring-slate-700 dark:bg-blue-900">
                                        <img class="rounded-full shadow-lg"
                                            src="https://flowbite.com/docs/images/people/profile-picture-1.jpg"
                                            alt="Jese Leos image">
                                    </span>
                                    <div
                                        class="justify-between items-center p-4 bg-white rounded-lg border border-gray-200 shadow-sm sm:flex dark:bg-gray-700 dark:border-gray-600">
                                        <time class="mb-1 text-xs font-normal text-gray-400 sm:order-last sm:mb-0">1
                                            day
                                            ago</time>
                                        <div class="text-sm font-normal text-gray-500 lex dark:text-gray-300">Jese
                                            Leos
                                            has
                                            changed <a href="#"
                                                class="font-semibold text-blue-600 dark:text-blue-500 hover:underline">Pricing
                                                page</a> task status to <span
                                                class="font-semibold text-gray-900 dark:text-white">Finished</span>
                                        </div>
                                    </div>
                                </li>
                            </ol>
                        </DisclosurePanel>
                    </div>
                    </template>
                    <template v-else>
                        <h3 class="ml-4"> No calls Available</h3>
                    </template>
                </Disclosure>
            </TabPanel>

            <!-- Ringing Tabls -->
            <TabPanel class="grid grid-cols-1 gap-4">
                <Disclosure>
                    <template v-if="people.ringing.length" v-for="{ items, index } in people.ringing" :key="index">
                        <div
                            class="w-full bg-white rounded-lg border border-gray-200 shadow-md dark:bg-gray-800 dark:border-gray-700">
                            <div class="w-full flex justify-between items-center px-4 py-3">
                                <div class="flex">
                                    <div class="flex items-center space-x-3">
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
                                        <div class="font-medium dark:text-white">
                                            <!-- <div v-show="items.agent_name == null">unknown </div> -->
                                            <div>{{ items.agent_name }}</div>
                                            <div class="text-xs text-gray-500 dark:text-gray-400">{{ items.call_time }}
                                            </div>
                                        </div>
                                    </div>
                                </div>

                                <div class="flex space-x-2 items-center font-normal text-sm dark:text-white">
                                    <span class="material-icons-outlined text-xl">person</span>
                                    <div class="space-y-0 text-xs">
                                        <div class="font-semibold">{{ items.contact_name }}</div>
                                        <div>{{ items.From }}</div>
                                    </div>
                                </div>

                                <div class="flex space-x-2 items-center font-normal text-sm dark:text-white">
                                    <span class="material-icons-outlined text-xl">timer</span>
                                    <span>00:06:13</span>
                                </div>

                                <button type="button"
                                    class="invisible1 text-white bg-green-700 hover:bg-green-800 focus:outline-none focus:ring-4 focus:ring-green-300 font-medium rounded-full text-sm p-2 h-8 w-8 text-center dark:bg-green-600 dark:hover:bg-green-700 dark:focus:ring-green-800 flex justify-center items-center"><span
                                        class="material-icons-outlined text-lg">local_phone</span></button>

                                <div class="flex space-x-2 items-center">
                                    <button type="button"
                                        class="hover:text-white dark:text-white bg-transparent hover:bg-gray-400 focus:outline-none focus:ring-0 focus:ring-gray-300 font-medium rounded-full text-sm px-1 py-1 dark:bg-gray-800 dark:hover:bg-gray-700 dark:focus:ring-gray-700 dark:border-gray-700 flex justify-center items-center">
                                        <span class="material-icons-outlined">more_vert</span>
                                    </button>
                                    <DisclosureButton type="button"
                                        class="hover:text-white dark:text-white bg-transparent hover:bg-gray-400 focus:outline-none focus:ring-0 focus:ring-gray-300 font-medium rounded-full text-sm px-1 py-1 dark:bg-gray-800 dark:hover:bg-gray-700 dark:focus:ring-gray-700 dark:border-gray-700 flex justify-center items-center">
                                        <span class="material-icons-outlined">arrow_drop_down</span>
                                    </DisclosureButton>
                                </div>
                            </div>

                            <!-- Open Content -->
                            <DisclosurePanel
                                class="py-2 px-4 bg-slate-100 dark:bg-slate-700 w-full rounded-b-lg max-h-72 overflow-auto scrollbar">
                                <div class="flex item-center w-full space-x-3 divide-x dark:divide-slate-500 mb-3">

                                    <div class="text-xs text-gray-500 dark:text-gray-400 flex items-center space-x-1">
                                        <div class="flex items-center space-x-1">
                                            <span class="material-icons-outlined text-lg">support_agent</span>
                                            <span class="font-bold">Agent Team:</span>
                                        </div>
                                        <span>{{ items.team_name }}</span>
                                    </div>

                                    <div
                                        class="text-xs text-gray-500 dark:text-gray-400 flex items-center space-x-1 pl-2">
                                        <div class="flex items-center space-x-1">
                                            <span class="material-icons-outlined text-lg">topic</span>
                                            <span class="font-bold">Interaction Topic:</span>
                                        </div>
                                        <span>Internet package upgrade</span>
                                    </div>
                                </div>

                                <div class="flex items-center space-x-3">
                                    <div class="text-base font-bold text-gray-500 dark:text-gray-400 mb-3">Call
                                        Recording:
                                    </div>

                                    <!-- <div
                                    class="px-3 py-2 mb-3 w-fit bg-white rounded-lg border border-gray-200 shadow-md dark:bg-gray-800 dark:border-gray-700 flex items-center space-x-3">
                                    <button type="button"
                                        class="py-2 px-3 text-xs font-medium text-center text-white bg-blue-700 rounded-full hover:bg-blue-800 focus:ring-4 focus:outline-none focus:ring-blue-300 dark:bg-blue-600 dark:hover:bg-blue-700 dark:focus:ring-blue-800 flex justify-center items-center h-7 w-7">
                                        <span class="material-icons">play_arrow</span>
                                        <span class="material-icons">stop</span>
                                    </button>

                                    <div class="text-base font-bold text-gray-500 dark:text-gray-400">00:00</div>
                                </div> -->
                                    <audio controls>
                                        <source :src="(items.recordings)" type="audio/ogg">
                                    </audio>
                                </div>


                                <div class="text-sm text-gray-500 dark:text-gray-400">
                                    <!-- <p class="mb-2">Dear John Bravo</p> -->

                                    <p>{{ items.CallNotes }}</p>
                                </div>


                                <ol class="relative border-l border-gray-200 dark:border-gray-700 mt-10 ml-5 mb-5">
                                    <li class="mb-10 ml-6">
                                        <span
                                            class="flex absolute -left-3 justify-center items-center w-6 h-6 bg-blue-200 rounded-full ring-8 ring-slate-100 dark:ring-slate-700 dark:bg-blue-900">
                                            <img class="rounded-full shadow-lg"
                                                src="https://flowbite.com/docs/images/people/profile-picture-3.jpg"
                                                alt="Bonnie image">
                                        </span>
                                        <div
                                            class="justify-between items-center p-4 bg-white rounded-lg border border-gray-200 shadow-sm sm:flex dark:bg-gray-700 dark:border-gray-600">
                                            <time
                                                class="mb-1 text-xs font-normal text-gray-400 sm:order-last sm:mb-0">just
                                                now</time>
                                            <div class="text-sm font-normal text-gray-500 dark:text-gray-300">Bonnie
                                                moved
                                                <a href="#"
                                                    class="font-semibold text-blue-600 dark:text-blue-500 hover:underline">Jese
                                                    Leos</a> to <span
                                                    class="bg-gray-100 text-gray-800 text-xs font-normal mr-2 px-2.5 py-0.5 rounded dark:bg-gray-600 dark:text-gray-300">Funny
                                                    Group</span>
                                            </div>
                                        </div>
                                    </li>
                                    <li class="mb-10 ml-6">
                                        <span
                                            class="flex absolute -left-3 justify-center items-center w-6 h-6 bg-blue-200 rounded-full ring-8 ring-slate-100 dark:ring-slate-700 dark:bg-blue-900">
                                            <img class="rounded-full shadow-lg"
                                                src="https://flowbite.com/docs/images/people/profile-picture-5.jpg"
                                                alt="Thomas Lean image">
                                        </span>
                                        <div
                                            class="p-4 bg-white rounded-lg border border-gray-200 shadow-sm dark:bg-gray-700 dark:border-gray-600">
                                            <div class="justify-between items-center mb-3 sm:flex">
                                                <time
                                                    class="mb-1 text-xs font-normal text-gray-400 sm:order-last sm:mb-0">2
                                                    hours ago</time>
                                                <div class="text-sm font-normal text-gray-500 lex dark:text-gray-300">
                                                    Thomas
                                                    Lean commented on <a href="#"
                                                        class="font-semibold text-gray-900 dark:text-white hover:underline">Flowbite
                                                        Pro</a></div>
                                            </div>
                                            <div
                                                class="p-3 text-xs italic font-normal text-gray-500 bg-gray-50 rounded-lg border border-gray-200 dark:bg-gray-600 dark:border-gray-500 dark:text-gray-300">
                                                Hi ya'll! I wanted to share a webinar zeroheight is having regarding how
                                                to
                                                best
                                                measure your design system! This is the second session of our new
                                                webinar
                                                series
                                                on #DesignSystems discussions where we'll be speaking about Measurement.
                                            </div>
                                        </div>
                                    </li>
                                    <li class="ml-6">
                                        <span
                                            class="flex absolute -left-3 justify-center items-center w-6 h-6 bg-blue-200 rounded-full ring-8 ring-slate-100 dark:ring-slate-700 dark:bg-blue-900">
                                            <img class="rounded-full shadow-lg"
                                                src="https://flowbite.com/docs/images/people/profile-picture-1.jpg"
                                                alt="Jese Leos image">
                                        </span>
                                        <div
                                            class="justify-between items-center p-4 bg-white rounded-lg border border-gray-200 shadow-sm sm:flex dark:bg-gray-700 dark:border-gray-600">
                                            <time class="mb-1 text-xs font-normal text-gray-400 sm:order-last sm:mb-0">1
                                                day
                                                ago</time>
                                            <div class="text-sm font-normal text-gray-500 lex dark:text-gray-300">Jese
                                                Leos
                                                has
                                                changed <a href="#"
                                                    class="font-semibold text-blue-600 dark:text-blue-500 hover:underline">Pricing
                                                    page</a> task status to <span
                                                    class="font-semibold text-gray-900 dark:text-white">Finished</span>
                                            </div>
                                        </div>
                                    </li>
                                </ol>
                            </DisclosurePanel>
                        </div>
                    </template>
                    <template v-else>
                        <h3 class="ml-4"> No calls Available</h3>
                    </template>
                </Disclosure>

            </TabPanel>

            <!-- Completed Tabls -->
            <TabPanel class="grid grid-cols-1 gap-4">
                <Skeleton v-if="people.length"></Skeleton>
                <Disclosure v-for="(items, index) in people.completed" :key="index">
                    <div
                        class="w-full bg-white rounded-lg border border-gray-200 shadow-md dark:bg-gray-800 dark:border-gray-700">
                        <div class="w-full flex justify-between items-center px-4 py-3">
                            <div class="flex">
                                <div class="flex items-center space-x-3">
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
                                    <div class="font-medium dark:text-white">
                                        <div v-show="items.agent_name == null">unknown </div>
                                        <div>{{ items.agent_name }}</div>
                                        <div class="text-xs text-gray-500 dark:text-gray-400">{{ items.call_time }}
                                        </div>
                                    </div>
                                </div>
                            </div>

                            <div class="flex space-x-2 items-center font-normal text-sm dark:text-white">
                                <span class="material-icons-outlined text-xl">person</span>
                                <div class="space-y-0 text-xs">

                                    <div v-if="items.agent_name != null" class="font-semibold">{{ items.contact_name }}
                                    </div>
                                    <div v-else class="font-semibold">unknown</div>

                                    <div>{{ items.From }}</div>
                                </div>
                            </div>

                            <div class="flex space-x-2 items-center font-normal text-sm dark:text-white">
                                <span class="material-icons-outlined text-xl">timer</span>
                                <span>00:06:13</span>
                            </div>

                            <button type="button"
                                class="invisible1 text-white bg-green-700 hover:bg-green-800 focus:outline-none focus:ring-4 focus:ring-green-300 font-medium rounded-full text-sm p-2 h-8 w-8 text-center dark:bg-green-600 dark:hover:bg-green-700 dark:focus:ring-green-800 flex justify-center items-center"><span
                                    class="material-icons-outlined text-lg">local_phone</span></button>

                            <div class="flex space-x-2 items-center">
                                <button type="button"
                                    class="hover:text-white dark:text-white bg-transparent hover:bg-gray-400 focus:outline-none focus:ring-0 focus:ring-gray-300 font-medium rounded-full text-sm px-1 py-1 dark:bg-gray-800 dark:hover:bg-gray-700 dark:focus:ring-gray-700 dark:border-gray-700 flex justify-center items-center">
                                    <span class="material-icons-outlined">more_vert</span>
                                </button>
                                <DisclosureButton type="button"
                                    @click="load_recordings('completed', index, items.CallSid)"
                                    class="hover:text-white dark:text-white bg-transparent hover:bg-gray-400 focus:outline-none focus:ring-0 focus:ring-gray-300 font-medium rounded-full text-sm px-1 py-1 dark:bg-gray-800 dark:hover:bg-gray-700 dark:focus:ring-gray-700 dark:border-gray-700 flex justify-center items-center">
                                    <span class="material-icons-outlined">arrow_drop_down</span>
                                </DisclosureButton>
                            </div>
                        </div>

                        <!-- Open Content -->
                        <DisclosurePanel
                            class="py-2 px-4 bg-slate-100 dark:bg-slate-700 w-full rounded-b-lg max-h-72 overflow-auto scrollbar">
                            <div class="flex item-center w-full space-x-3 divide-x dark:divide-slate-500 mb-3">

                                <div class="text-xs text-gray-500 dark:text-gray-400 flex items-center space-x-1">
                                    <div class="flex items-center space-x-1">
                                        <span class="material-icons-outlined text-lg">support_agent</span>
                                        <span class="font-bold">Agent Team:</span>
                                    </div>
                                    <span>{{ items.team_name }}</span>
                                </div>

                                <div class="text-xs text-gray-500 dark:text-gray-400 flex items-center space-x-1 pl-2">
                                    <div class="flex items-center space-x-1">
                                        <span class="material-icons-outlined text-lg">topic</span>
                                        <span class="font-bold">Interaction Topic:</span>
                                    </div>
                                    <span>Internet package upgrade</span>
                                </div>
                            </div>
                            <div class="flex items-center space-x-3">
                                <div class="text-base font-bold text-gray-500 dark:text-gray-400 mb-3">Call
                                    Recording:
                                </div>
                                <template v-if="items.recordings.length" v-for="rec in items.recordings">
                                    <audio controls>
                                        <source :src="rec" type="audio/ogg">
                                    </audio>
                                </template>
                                <template v-else>
                                    <h3> No Recordings Available</h3>

                                </template>
                            </div>
                            <div class="text-sm text-gray-500 dark:text-gray-400">
                                <!-- <p class="mb-2">Dear John Bravo</p> -->

                                <p>{{ items.CallNotes }}</p>
                            </div>
                            <ol class="relative border-l border-gray-200 dark:border-gray-700 mt-10 ml-5 mb-5">
                                <li class="mb-10 ml-6">
                                    <span
                                        class="flex absolute -left-3 justify-center items-center w-6 h-6 bg-blue-200 rounded-full ring-8 ring-slate-100 dark:ring-slate-700 dark:bg-blue-900">
                                        <img class="rounded-full shadow-lg"
                                            src="https://flowbite.com/docs/images/people/profile-picture-3.jpg"
                                            alt="Bonnie image">
                                    </span>
                                    <div
                                        class="justify-between items-center p-4 bg-white rounded-lg border border-gray-200 shadow-sm sm:flex dark:bg-gray-700 dark:border-gray-600">
                                        <time class="mb-1 text-xs font-normal text-gray-400 sm:order-last sm:mb-0">just
                                            now</time>
                                        <div class="text-sm font-normal text-gray-500 dark:text-gray-300">Bonnie
                                            moved
                                            <a href="#"
                                                class="font-semibold text-blue-600 dark:text-blue-500 hover:underline">Jese
                                                Leos</a> to <span
                                                class="bg-gray-100 text-gray-800 text-xs font-normal mr-2 px-2.5 py-0.5 rounded dark:bg-gray-600 dark:text-gray-300">Funny
                                                Group</span>
                                        </div>
                                    </div>
                                </li>
                                <li class="mb-10 ml-6">
                                    <span
                                        class="flex absolute -left-3 justify-center items-center w-6 h-6 bg-blue-200 rounded-full ring-8 ring-slate-100 dark:ring-slate-700 dark:bg-blue-900">
                                        <img class="rounded-full shadow-lg"
                                            src="https://flowbite.com/docs/images/people/profile-picture-5.jpg"
                                            alt="Thomas Lean image">
                                    </span>
                                    <div
                                        class="p-4 bg-white rounded-lg border border-gray-200 shadow-sm dark:bg-gray-700 dark:border-gray-600">
                                        <div class="justify-between items-center mb-3 sm:flex">
                                            <time class="mb-1 text-xs font-normal text-gray-400 sm:order-last sm:mb-0">2
                                                hours ago</time>
                                            <div class="text-sm font-normal text-gray-500 lex dark:text-gray-300">
                                                Thomas
                                                Lean commented on <a href="#"
                                                    class="font-semibold text-gray-900 dark:text-white hover:underline">Flowbite
                                                    Pro</a></div>
                                        </div>
                                        <div
                                            class="p-3 text-xs italic font-normal text-gray-500 bg-gray-50 rounded-lg border border-gray-200 dark:bg-gray-600 dark:border-gray-500 dark:text-gray-300">
                                            Hi ya'll! I wanted to share a webinar zeroheight is having regarding how
                                            to
                                            best
                                            measure your design system! This is the second session of our new
                                            webinar
                                            series
                                            on #DesignSystems discussions where we'll be speaking about Measurement.
                                        </div>
                                    </div>
                                </li>
                                <li class="ml-6">
                                    <span
                                        class="flex absolute -left-3 justify-center items-center w-6 h-6 bg-blue-200 rounded-full ring-8 ring-slate-100 dark:ring-slate-700 dark:bg-blue-900">
                                        <img class="rounded-full shadow-lg"
                                            src="https://flowbite.com/docs/images/people/profile-picture-1.jpg"
                                            alt="Jese Leos image">
                                    </span>
                                    <div
                                        class="justify-between items-center p-4 bg-white rounded-lg border border-gray-200 shadow-sm sm:flex dark:bg-gray-700 dark:border-gray-600">
                                        <time class="mb-1 text-xs font-normal text-gray-400 sm:order-last sm:mb-0">1
                                            day
                                            ago</time>
                                        <div class="text-sm font-normal text-gray-500 lex dark:text-gray-300">Jese
                                            Leos
                                            has
                                            changed <a href="#"
                                                class="font-semibold text-blue-600 dark:text-blue-500 hover:underline">Pricing
                                                page</a> task status to <span
                                                class="font-semibold text-gray-900 dark:text-white">Finished</span>
                                        </div>
                                    </div>
                                </li>
                            </ol>
                        </DisclosurePanel>
                    </div>
                </Disclosure>
            </TabPanel>
        </TabPanels>

    </TabGroup>
</template>

<script>
import {
    Disclosure,
    DisclosureButton,
    DisclosurePanel,
    TabGroup,
    TabList,
    Tab,
    TabPanels,
    TabPanel
} from '@headlessui/vue'
import axios from 'axios'
import Skeleton from './Skeleton.vue'
export default {
    components: {
        Disclosure,
        DisclosureButton,
        DisclosurePanel,
        TabGroup,
        TabList,
        Tab,
        TabPanels,
        TabPanel,
        Skeleton

    },
    data() {
        return {
            people: {
                ongoing: [],
                completed: [],
                ringing: []
            },
            // record: [],
            seen: true,
            // currentTrack: null,
            activeTab: "ongoing",
        }
    },

    async mounted() {
        this.load_calls()
    },
    methods: {
        load_calls() {

            axios.get('http://localhost/Php_Database_callCenter/Calls.php')
                .then(response => {

                    this.people = response.data

                })
                .catch(function (error) {
                    // handle error
                });
        },
        load_recordings(type, index, CallSid) {

            axios.get('http://localhost/Api_Twilio/FindCallRecordings.php', { params: { CallSid: CallSid } })
                .then(response => {
                    if (type == "completed") {
                        this.people.completed[index].recordings = response.data
                        
                    }
                })
                .catch(function (error) {
                    // handle error
                });
        },

    },
    computed:
    {
        ongoingCount() {
            var total = 0;
            total = total + this.people.ongoing.length
            return total
        },
        ringingCount() {
            var total = 0;
            total = total + this.people.ringing.length
            return total
        },
        completedCount() {
            var total = 0;
            total = total + this.people.completed.length
            return total
        },
        // ...mapGetters(['userMetaRole'])
    },


}
</script>