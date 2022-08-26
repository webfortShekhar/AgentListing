<template>
    <div class="pl-2 pr-2 py-3">
        <div class="mb-0">
            <TabGroup>
                <TabList>
                    <div class="border-0 border-gray-200 dark:border-gray-700">
                        <div class="flex -mb-px text-sm font-medium text-center text-gray-500 dark:text-gray-400">
                            <Tab class="flex items-center mr-2 px-1 py-3 text-blue-600 rounded-t-lg border-b-2 border-blue-600 focus:outline-none dark:text-blue-500 dark:border-blue-500 group"
                                aria-current="page">
                                <div class="mx-1">Online</div>
                                <span
                                    class="bg-blue-100 text-blue-800 text-xs font-semibold mr-2 px-1 py-0 rounded dark:bg-blue-200 dark:text-blue-800">9+</span>
                            </Tab>
                            <Tab
                                class="flex items-center mr-2 px-1 py-3 rounded-t-lg border-b-2 border-transparent focus:outline-none hover:text-gray-600 hover:border-gray-300 dark:hover:text-gray-300 group">
                                <div class="mx-1">Break</div>
                                <span
                                    class="bg-blue-100 text-blue-800 text-xs font-semibold mr-2 px-1 py-0 rounded dark:bg-blue-200 dark:text-blue-800">9+</span>
                            </Tab>
                            <Tab
                                class="flex items-center px-1 py-3 rounded-t-lg border-b-2 border-transparent focus:outline-none hover:text-gray-600 hover:border-gray-300 dark:hover:text-gray-300 group">
                                <div class="mx-1">Offline</div>
                                <span
                                    class="bg-blue-100 text-blue-800 text-xs font-semibold mr-2 px-1 py-0 rounded dark:bg-blue-200 dark:text-blue-800">9+</span>
                            </Tab>
                        </div>
                    </div>
                </TabList>

                <TabPanels>
                    <div class="mt-3">
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

                    <div class="mt-3 mb-0 pr-1 overflow-auto h-[calc(100vh_-_194px)] scrollbar">

                        <!-- Tab Online Panel -->
                        <TabPanel>
                            <div class="space-y-1">
                                <div class="flex items-center pt-2">
                                    <div class="text-xs font-light dark:text-gray-50 mb-0 flex items-center space-x-1">
                                        <span class="material-icons-outlined text-sm">support_agent</span>
                                        <div class="truncate w-32">Team Pro</div>
                                    </div>
                                </div>
                                <div v-for="index in 2" :key="index"
                                    class="py-2 px-2 bg-slate-100 dark:bg-slate-700 rounded-lg w-full space-y-3">
                                    <div class="flex items-center space-x-2 w-full">
                                        <div class="relative">
                                            <img class="w-8 h-8 max-h-fit max-w-fit rounded-full"
                                                src="https://flowbite.com/docs/images/people/profile-picture-5.jpg"
                                                alt="">
                                            <span
                                                class="bottom-0 left-5 absolute  w-3 h-3 bg-green-400 border-2 border-white dark:border-gray-800 rounded-full"></span>
                                        </div>
                                        <div class="w-full flex justify-between">
                                            <div class="mr-1 w-10/12">
                                                <div class="text-xs font-bold dark:text-gray-50 mb-0 truncate w-48">
                                                    Kishan
                                                    Kumar</div>
                                                <div class="flex items-center">
                                                    <div
                                                        class="text-xs font-light dark:text-gray-50 mb-0 flex items-center space-x-1">
                                                        <span class="material-icons-outlined text-sm">groups</span>
                                                        <div class="truncate w-48">In meetings</div>
                                                    </div>
                                                </div>
                                            </div>

                                            <div class="ml-1 flex justify-end items-center">
                                                <button type="button"
                                                    class="text-white bg-green-700 hover:bg-green-800 focus:outline-none focus:ring-4 focus:ring-green-300 font-medium rounded-full text-sm p-2 h-8 w-8 text-center dark:bg-green-600 dark:hover:bg-green-700 dark:focus:ring-green-800 flex justify-center items-center"><span
                                                        class="material-icons-outlined text-lg">local_phone</span></button>
                                            </div>
                                        </div>
                                    </div>
                                </div>

                                <div class="flex items-center pt-2">
                                    <div class="text-xs font-light dark:text-gray-50 mb-0 flex items-center space-x-1">
                                        <span class="material-icons-outlined text-sm">support_agent</span>
                                        <div class="truncate w-32">Oye Team</div>
                                    </div>
                                </div>
                                <div v-for="index in 6" :key="index"
                                    class="py-2 px-2 bg-slate-100 dark:bg-slate-700 rounded-lg w-full space-y-1">
                                    <div class="flex items-center space-x-2 w-full">
                                        <div class="relative">
                                            <img class="w-8 h-8 max-h-fit max-w-fit rounded-full"
                                                src="https://flowbite.com/docs/images/people/profile-picture-5.jpg"
                                                alt="">
                                            <span
                                                class="bottom-0 left-5 absolute  w-3 h-3 bg-green-400 border-2 border-white dark:border-gray-800 rounded-full"></span>
                                        </div>
                                        <div class="w-full flex justify-between">
                                            <div class="mr-1 w-10/12">
                                                <div class="text-xs font-bold dark:text-gray-50 mb-0 truncate w-48">
                                                    Kishan
                                                    Kumar</div>
                                                <div class="flex items-center">
                                                    <div
                                                        class="text-xs font-light dark:text-gray-50 mb-0 flex items-center space-x-1">
                                                        <span class="material-icons-outlined text-sm">groups</span>
                                                        <div class="truncate w-48">In meetings</div>
                                                    </div>
                                                </div>
                                            </div>

                                            <div class="ml-1 flex justify-end items-center">
                                                <button type="button"
                                                    class="text-white bg-green-700 hover:bg-green-800 focus:outline-none focus:ring-4 focus:ring-green-300 font-medium rounded-full text-sm p-2 h-8 w-8 text-center dark:bg-green-600 dark:hover:bg-green-700 dark:focus:ring-green-800 flex justify-center items-center"><span
                                                        class="material-icons-outlined text-lg">local_phone</span></button>
                                            </div>
                                        </div>
                                    </div>
                                </div>
                            </div>
                        </TabPanel>

                        <!-- Tab Break Panel -->
                        <TabPanel>
                            <div class="space-y-1">
                                <div class="flex items-center pt-2">
                                    <div class="text-xs font-light dark:text-gray-50 mb-0 flex items-center space-x-1">
                                        <span class="material-icons-outlined text-sm">support_agent</span>
                                        <div class="truncate w-32">Team Pro</div>
                                    </div>
                                </div>
                                <div v-for="index in 2" :key="index"
                                    class="py-2 px-2 bg-slate-100 dark:bg-slate-700 rounded-lg w-full space-y-3">
                                    <div class="flex items-center space-x-2 w-full">
                                        <div class="relative">
                                            <img class="w-8 h-8 max-h-fit max-w-fit rounded-full"
                                                src="https://flowbite.com/docs/images/people/profile-picture-5.jpg"
                                                alt="">
                                            <span
                                                class="bottom-0 left-5 absolute  w-3 h-3 bg-yellow-400 border-2 border-white dark:border-gray-800 rounded-full"></span>
                                        </div>
                                        <div class="w-full flex justify-between">
                                            <div class="mr-1 w-8/12">
                                                <div class="text-xs font-bold dark:text-gray-50 mb-0 truncate w-32">
                                                    Kishan
                                                    Kumar</div>
                                                <div class="flex items-center">
                                                    <div
                                                        class="text-xs font-light dark:text-gray-50 mb-0 flex items-center space-x-1">
                                                        <span
                                                            class="material-icons-outlined text-yellow-700 dark:text-yellow-400 text-sm">free_breakfast</span>
                                                        <div class="truncate w-32 text-yellow-700 dark:text-yellow-400">
                                                            Gym Break</div>
                                                    </div>
                                                </div>
                                            </div>

                                            <div class="ml-1 flex justify-end items-center">
                                                <span
                                                    class="bg-gray-700 text-gray-300 text-xs font-medium inline-flex items-center px-1 py-0 rounded mr-2 dark:bg-gray-100 dark:text-gray-800">
                                                        <svg aria-hidden="true" class="mr-1 w-3 h-3" fill="currentColor"
                                                            viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg">
                                                            <path fill-rule="evenodd"
                                                                d="M10 18a8 8 0 100-16 8 8 0 000 16zm1-12a1 1 0 10-2 0v4a1 1 0 00.293.707l2.828 2.829a1 1 0 101.415-1.415L11 9.586V6z"
                                                                clip-rule="evenodd"></path>
                                                        </svg>
                                                        00:05
                                                </span>
                                            </div>
                                        </div>
                                    </div>
                                </div>

                                <div class="flex items-center pt-2">
                                    <div class="text-xs font-light dark:text-gray-50 mb-0 flex items-center space-x-1">
                                        <span class="material-icons-outlined text-sm">support_agent</span>
                                        <div class="truncate w-32">Oye Team</div>
                                    </div>
                                </div>
                                <div v-for="index in 10" :key="index"
                                    class="py-2 px-2 bg-slate-100 dark:bg-slate-700 rounded-lg w-full space-y-3">
                                    <div class="flex items-center space-x-2 w-full">
                                        <div class="relative">
                                            <img class="w-8 h-8 max-h-fit max-w-fit rounded-full"
                                                src="https://flowbite.com/docs/images/people/profile-picture-5.jpg"
                                                alt="">
                                            <span
                                                class="bottom-0 left-5 absolute  w-3 h-3 bg-yellow-400 border-2 border-white dark:border-gray-800 rounded-full"></span>
                                        </div>
                                        <div class="w-full flex justify-between">
                                            <div class="mr-1 w-8/12">
                                                <div class="text-xs font-bold dark:text-gray-50 mb-0 truncate w-32">
                                                    Kishan
                                                    Kumar</div>
                                                <div class="flex items-center">
                                                    <div
                                                        class="text-xs font-light dark:text-gray-50 mb-0 flex items-center space-x-1">
                                                        <span
                                                            class="material-icons-outlined text-yellow-700 dark:text-yellow-400 text-sm">free_breakfast</span>
                                                        <div class="truncate w-32 text-yellow-700 dark:text-yellow-400">
                                                            Gym Break</div>
                                                    </div>
                                                </div>
                                            </div>

                                            <div class="ml-1 flex justify-end items-center">
                                                <span
                                                    class="bg-gray-700 text-gray-300 text-xs font-medium inline-flex items-center px-1 py-0 rounded mr-2 dark:bg-gray-100 dark:text-gray-800">
                                                        <svg aria-hidden="true" class="mr-1 w-3 h-3" fill="currentColor"
                                                            viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg">
                                                            <path fill-rule="evenodd"
                                                                d="M10 18a8 8 0 100-16 8 8 0 000 16zm1-12a1 1 0 10-2 0v4a1 1 0 00.293.707l2.828 2.829a1 1 0 101.415-1.415L11 9.586V6z"
                                                                clip-rule="evenodd"></path>
                                                        </svg>
                                                        00:05
                                                </span>
                                            </div>
                                        </div>
                                    </div>
                                </div>
                            </div>
                        </TabPanel>

                        <!-- Tab Offline Panel -->
                        <TabPanel>
                            <div class="space-y-1">
                                <div class="flex items-center pt-2">
                                    <div class="text-xs font-light dark:text-gray-50 mb-0 flex items-center space-x-1">
                                        <span class="material-icons-outlined text-sm">support_agent</span>
                                        <div class="truncate w-32">Team Pro</div>
                                    </div>
                                </div>
                                <div v-for="index in 2" :key="index"
                                    class="py-2 px-2 bg-slate-100 dark:bg-slate-700 rounded-lg w-full space-y-3">
                                    <div class="flex items-center space-x-2 w-full">
                                        <div class="relative">
                                            <img class="w-8 h-8 max-h-fit max-w-fit rounded-full"
                                                src="https://flowbite.com/docs/images/people/profile-picture-5.jpg"
                                                alt="">
                                            <span
                                                class="bottom-0 left-5 absolute  w-3 h-3 bg-red-400 border-2 border-white dark:border-gray-800 rounded-full"></span>
                                        </div>
                                        <div class="w-full flex justify-between">
                                            <div class="mr-1 w-10/12">
                                                <div class="text-xs font-bold dark:text-gray-50 mb-0 truncate w-48">
                                                    Kishan
                                                    Kumar</div>
                                                <div class="flex items-center">
                                                    <div
                                                        class="text-xs font-light text-red-400 dark:text-red-300 mb-0 flex items-center space-x-1">
                                                        <span class="material-icons-outlined text-sm">person_off</span>
                                                        <div class="truncate w-48">Away</div>
                                                    </div>
                                                </div>
                                            </div>

                                            <div class="ml-1 flex justify-end items-center">
                                                <button type="button"
                                                    class="text-white cursor-not-allowed bg-green-500 hover:bg-green-500 focus:outline-none focus:ring-4 focus:ring-green-300 font-medium rounded-full text-sm p-2 h-8 w-8 text-center dark:bg-green-500 dark:hover:bg-green-500 dark:focus:ring-green-800 flex justify-center items-center"
                                                    disabled><span
                                                        class="material-icons-outlined text-lg">phone_disabled</span></button>
                                            </div>
                                        </div>
                                    </div>
                                </div>

                                <div class="flex items-center pt-2">
                                    <div class="text-xs font-light dark:text-gray-50 mb-0 flex items-center space-x-1">
                                        <span class="material-icons-outlined text-sm">support_agent</span>
                                        <div class="truncate w-32">Oye Team</div>
                                    </div>
                                </div>
                                <div v-for="index in 6" :key="index"
                                    class="py-2 px-2 bg-slate-100 dark:bg-slate-700 rounded-lg w-full space-y-1">
                                    <div class="flex items-center space-x-2 w-full">
                                        <div class="relative">
                                            <img class="w-8 h-8 max-h-fit max-w-fit rounded-full"
                                                src="https://flowbite.com/docs/images/people/profile-picture-5.jpg"
                                                alt="">
                                            <span
                                                class="bottom-0 left-5 absolute  w-3 h-3 bg-red-400 border-2 border-white dark:border-gray-800 rounded-full"></span>
                                        </div>
                                        <div class="w-full flex justify-between">
                                            <div class="mr-1 w-10/12">
                                                <div class="text-xs font-bold dark:text-gray-50 mb-0 truncate w-48">
                                                    Kishan
                                                    Kumar</div>
                                                <div class="flex items-center">
                                                    <div
                                                        class="text-xs font-light text-red-400 dark:text-red-300 mb-0 flex items-center space-x-1">
                                                        <span class="material-icons-outlined text-sm">person_off</span>
                                                        <div class="truncate w-48">Away</div>
                                                    </div>
                                                </div>
                                            </div>

                                            <div class="ml-1 flex justify-end items-center">
                                                <button type="button"
                                                    class="text-white cursor-not-allowed bg-green-500 hover:bg-green-500 focus:outline-none focus:ring-4 focus:ring-green-300 font-medium rounded-full text-sm p-2 h-8 w-8 text-center dark:bg-green-500 dark:hover:bg-green-500 dark:focus:ring-green-800 flex justify-center items-center"
                                                    disabled><span
                                                        class="material-icons-outlined text-lg">phone_disabled</span></button>
                                            </div>
                                        </div>
                                    </div>
                                </div>
                            </div>
                        </TabPanel>
                    </div>
                </TabPanels>
            </TabGroup>
        </div>
    </div>
</template>

<script>
import { TabGroup, TabList, Tab, TabPanels, TabPanel } from '@headlessui/vue'

export default {
    components: {
        TabGroup, TabList, Tab, TabPanels, TabPanel
    }
}
</script>