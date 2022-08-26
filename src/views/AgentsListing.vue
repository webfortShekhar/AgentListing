<template>
    <div class="h-screen w-screen fixed top-0 left-0 bottom-0 right-0 bg-white dark:bg-zinc-800 overflow-hidden">
        <Header />

        <section class="mt-16">
            <div class="h-[calc(100vh_-_64px)] overflow-auto scrollbar scrollbar">
                <div class="container mx-auto px-4 py-8">
                    <div class="mb-5">
                        <div
                            class="mb-8 text-3xl font-extrabold tracking-tight leading-none text-gray-900 md:text-4xl dark:text-white">
                            Agents List</div>

                        <div class="grid grid-cols-5 gap-4 w-full">
                            <div class="relative">
                                <input type="text" id="agent_name"
                                    class="block px-2.5 pb-1.5 pt-3 w-full text-sm text-gray-900 bg-transparent rounded-lg border-1 border-gray-300 appearance-none dark:text-white dark:border-gray-600 dark:focus:border-blue-500 focus:outline-none focus:ring-0 focus:border-blue-600 peer"
                                    placeholder=" " />
                                <label for="agent_name"
                                    class="absolute text-sm text-gray-500 dark:text-gray-400 duration-300 transform -translate-y-3 scale-75 top-1 z-10 origin-[0] bg-white dark:bg-zinc-800 px-2 peer-focus:px-2 peer-focus:text-blue-600 peer-focus:dark:text-blue-500 peer-placeholder-shown:scale-100 peer-placeholder-shown:-translate-y-1/2 peer-placeholder-shown:top-1/2 peer-focus:top-1 peer-focus:scale-75 peer-focus:-translate-y-3 left-1">Agent
                                    Name</label>
                            </div>

                            <div class="relative">
                                <input type="text" id="agent_id"
                                    class="block px-2.5 pb-1.5 pt-3 w-full text-sm text-gray-900 bg-transparent rounded-lg border-1 border-gray-300 appearance-none dark:text-white dark:border-gray-600 dark:focus:border-blue-500 focus:outline-none focus:ring-0 focus:border-blue-600 peer"
                                    placeholder=" " />
                                <label for="agent_id"
                                    class="absolute text-sm text-gray-500 dark:text-gray-400 duration-300 transform -translate-y-3 scale-75 top-1 z-10 origin-[0] bg-white dark:bg-zinc-800 px-2 peer-focus:px-2 peer-focus:text-blue-600 peer-focus:dark:text-blue-500 peer-placeholder-shown:scale-100 peer-placeholder-shown:-translate-y-1/2 peer-placeholder-shown:top-1/2 peer-focus:top-1 peer-focus:scale-75 peer-focus:-translate-y-3 left-1">Agent
                                    Id</label>
                            </div>

                            <div class="relative">
                                <select id="select_team" 
                                    class="block w-full rounded-lg border border-gray-300 bg-white dark:bg-zinc-800 px-2.5 pb-1.5 pt-3 text-sm text-gray-900 focus:border-blue-500 focus:ring-blue-500 dark:border-gray-600 dark:text-white dark:placeholder-gray-400 dark:focus:border-blue-500 dark:focus:ring-blue-500">
                                    <template v-for="index in agent_teams.teams_data" :key="index">
                                        <option value="US">{{ index.team_name }}</option>
                                    </template>
                                </select><label for="select_team"
                                    class="absolute top-1 left-1 z-10 origin-[0] -translate-y-3 scale-75 transform bg-white px-2 text-sm text-gray-500 duration-300 peer-placeholder-shown:top-1/2 peer-placeholder-shown:-translate-y-1/2 peer-placeholder-shown:scale-100 peer-focus:top-1 peer-focus:-translate-y-3 peer-focus:scale-75 peer-focus:px-2 peer-focus:text-blue-600 dark:bg-zinc-800 dark:text-gray-400 peer-focus:dark:text-blue-500">Select
                                    Team</label>
                            </div>

                            <div class="relative">
                                <select id="select_role"
                                    class="block w-full rounded-lg border border-gray-300 bg-white dark:bg-zinc-800 px-2.5 pb-1.5 pt-3 text-sm text-gray-900 focus:border-blue-500 focus:ring-blue-500 dark:border-gray-600 dark:text-white dark:placeholder-gray-400 dark:focus:border-blue-500 dark:focus:ring-blue-500">
                                    <option value="US">United States</option>
                                    <option value="CA">Canada</option>
                                    <option value="FR">France</option>
                                    <option value="DE">Germany</option>
                                </select><label for="select_role"
                                    class="absolute top-1 left-1 z-10 origin-[0] -translate-y-3 scale-75 transform bg-white px-2 text-sm text-gray-500 duration-300 peer-placeholder-shown:top-1/2 peer-placeholder-shown:-translate-y-1/2 peer-placeholder-shown:scale-100 peer-focus:top-1 peer-focus:-translate-y-3 peer-focus:scale-75 peer-focus:px-2 peer-focus:text-blue-600 dark:bg-zinc-800 dark:text-gray-400 peer-focus:dark:text-blue-500">Select
                                    Role</label>
                            </div>

                            <button type="button" @click="agent_info(team_name)"
                                class="text-white bg-gradient-to-r w-fit from-blue-500 via-blue-600 to-blue-700 hover:bg-gradient-to-br focus:ring-4 focus:outline-none focus:ring-blue-300 dark:focus:ring-blue-800 font-medium rounded-lg text-sm px-10 py-1.5 text-center uppercase flex items-center space-x-1">
                                <div class="material-icons-outlined text-lg"> search </div>
                                <div>search</div>
                            </button>
                        </div>
                    </div>
                    <table class="w-full text-sm text-left text-gray-500 dark:text-gray-400 shadow-md rounded-xl">
                        <thead class="text-xs text-gray-700 uppercase bg-gray-50 dark:bg-gray-700 dark:text-gray-400">
                            <tr>
                                <th scope="col" class="p-4 rounded-tl-xl">
                                    <div class="flex items-center">
                                        <input id="checkbox-all-search" type="checkbox"
                                            class="w-4 h-4 text-blue-600 bg-gray-100 rounded border-gray-300 focus:ring-blue-500 dark:focus:ring-blue-600 dark:ring-offset-gray-800 focus:ring-2 dark:bg-gray-700 dark:border-gray-600">
                                        <label for="checkbox-all-search" class="sr-only">checkbox</label>
                                    </div>
                                </th>
                                <th scope="col" class="py-3 px-6">
                                    Agent Name
                                </th>
                                <th scope="col" class="py-3 px-6">
                                    Agent ID
                                </th>
                                <th scope="col" class="py-3 px-6">
                                    Team
                                </th>
                                <th scope="col" class="py-3 px-6">
                                    Role
                                </th>
                                <th scope="col" class="py-3 px-6">
                                    Status
                                </th>
                                <th scope="col" class="py-3 px-6 rounded-tr-xl">
                                    Action
                                </th>
                            </tr>
                        </thead>
                        <tbody>
                            <template v-for="index in agents.Agent_list" :key="index">
                                <tr
                                    class="bg-white border-b dark:bg-gray-800 dark:border-gray-700 hover:bg-gray-50 dark:hover:bg-gray-600">
                                    <td class="p-4 w-4 bg-blue-50 dark:bg-gray-900">
                                        <div class="flex items-center">
                                            <input id="checkbox-table-search-1" type="checkbox"
                                                class="w-4 h-4 text-blue-600 bg-gray-100 rounded border-gray-300 focus:ring-blue-500 dark:focus:ring-blue-600 dark:ring-offset-gray-800 focus:ring-2 dark:bg-gray-700 dark:border-gray-600">
                                            <label for="checkbox-table-search-1" class="sr-only">checkbox</label>
                                        </div>
                                    </td>
                                    <th scope="row"
                                        class="flex items-center py-4 px-6 text-gray-900 whitespace-nowrap dark:text-white bg-blue-50 dark:bg-gray-900">
                                        <img class="w-10 h-10 rounded-full" :src="index.google_profile_picture"
                                            :alt="index.agent_name">
                                        <div class="pl-3">
                                            <div class="text-base font-semibold">{{ index.agent_name }}</div>
                                            <div class="font-normal text-gray-500">{{ index.email }}</div>
                                        </div>
                                    </th>
                                    <td class="py-4 px-6">
                                        #123587
                                    </td>
                                    <td class="py-4 px-6">
                                        {{ index.team_name }}
                                    </td>
                                    <td class="py-4 px-6">
                                        {{ index.role }}
                                    </td>
                                    <td class="py-4 px-6">
                                        <div class="flex items-center">
                                            <div class="h-2.5 w-2.5 rounded-full bg-green-400 mr-2"></div>
                                            {{ index.login_status }}
                                        </div>
                                    </td>
                                    <td class="py-4 px-6">
                                        <a href="#"
                                            class="font-medium text-blue-600 dark:text-blue-500 hover:underline">Edit</a>
                                    </td>
                                </tr>
                            </template>
                            <tr class="bg-white dark:bg-gray-800 hover:bg-gray-50 dark:hover:bg-gray-600">
                                <td class="p-4 w-4 rounded-bl-xl bg-blue-50 dark:bg-gray-900">
                                    <div class="flex items-center">
                                        <input id="checkbox-table-search-3" type="checkbox"
                                            class="w-4 h-4 text-blue-600 bg-gray-100 rounded border-gray-300 focus:ring-blue-500 dark:focus:ring-blue-600 dark:ring-offset-gray-800 focus:ring-2 dark:bg-gray-700 dark:border-gray-600">
                                        <label for="checkbox-table-search-3" class="sr-only">checkbox</label>
                                    </div>
                                </td>
                                <th scope="row"
                                    class="flex items-center py-4 px-6 font-medium text-gray-900 whitespace-nowrap dark:text-white bg-blue-50 dark:bg-gray-900">
                                    <img class="w-10 h-10 rounded-full"
                                        src="https://flowbite.com/docs/images/people/profile-picture-4.jpg"
                                        alt="Jese image">
                                    <div class="pl-3">
                                        <div class="text-base font-semibold">Leslie Livingston</div>
                                        <div class="font-normal text-gray-500">leslie@flowbite.com</div>
                                    </div>
                                </th>
                                <td class="py-4 px-6">
                                    #123587
                                </td>
                                <td class="py-4 px-6">
                                    Sale team
                                </td>
                                <td class="py-4 px-6">
                                    SEO Specialist
                                </td>
                                <td class="py-4 px-6">
                                    <div class="flex items-center">
                                        <div class="h-2.5 w-2.5 rounded-full bg-red-500 mr-2"></div> Offline
                                    </div>
                                </td>
                                <td class="py-4 px-6 rounded-br-xl">
                                    <a href="#"
                                        class="font-medium text-blue-600 dark:text-blue-500 hover:underline">Edit</a>
                                </td>
                            </tr>
                        </tbody>
                    </table>

                    <nav class="flex justify-between items-center pt-4" aria-label="Table navigation">
                        <span class="text-sm font-normal text-gray-500 dark:text-gray-400">Showing <span
                                class="font-semibold text-gray-900 dark:text-white">1-10</span> of <span
                                class="font-semibold text-gray-900 dark:text-white">1000</span></span>
                        <ul class="inline-flex items-center -space-x-px">
                            <li>
                                <a href="#"
                                    class="block py-2 px-3 ml-0 leading-tight text-gray-500 bg-white rounded-l-lg border border-gray-300 hover:bg-gray-100 hover:text-gray-700 dark:bg-gray-800 dark:border-gray-700 dark:text-gray-400 dark:hover:bg-gray-700 dark:hover:text-white">
                                    <span class="sr-only">Previous</span>
                                    <svg class="w-5 h-5" aria-hidden="true" fill="currentColor" viewBox="0 0 20 20"
                                        xmlns="http://www.w3.org/2000/svg">
                                        <path fill-rule="evenodd"
                                            d="M12.707 5.293a1 1 0 010 1.414L9.414 10l3.293 3.293a1 1 0 01-1.414 1.414l-4-4a1 1 0 010-1.414l4-4a1 1 0 011.414 0z"
                                            clip-rule="evenodd"></path>
                                    </svg>
                                </a>
                            </li>
                            <li>
                                <a href="#"
                                    class="py-2 px-3 leading-tight text-gray-500 bg-white border border-gray-300 hover:bg-gray-100 hover:text-gray-700 dark:bg-gray-800 dark:border-gray-700 dark:text-gray-400 dark:hover:bg-gray-700 dark:hover:text-white">1</a>
                            </li>
                            <li>
                                <a href="#"
                                    class="py-2 px-3 leading-tight text-gray-500 bg-white border border-gray-300 hover:bg-gray-100 hover:text-gray-700 dark:bg-gray-800 dark:border-gray-700 dark:text-gray-400 dark:hover:bg-gray-700 dark:hover:text-white">2</a>
                            </li>
                            <li>
                                <a href="#" aria-current="page"
                                    class="z-10 py-2 px-3 leading-tight text-blue-600 bg-blue-50 border border-blue-300 hover:bg-blue-100 hover:text-blue-700 dark:border-gray-700 dark:bg-gray-700 dark:text-white">3</a>
                            </li>
                            <li>
                                <a href="#"
                                    class="py-2 px-3 leading-tight text-gray-500 bg-white border border-gray-300 hover:bg-gray-100 hover:text-gray-700 dark:bg-gray-800 dark:border-gray-700 dark:text-gray-400 dark:hover:bg-gray-700 dark:hover:text-white">...</a>
                            </li>
                            <li>
                                <a href="#"
                                    class="py-2 px-3 leading-tight text-gray-500 bg-white border border-gray-300 hover:bg-gray-100 hover:text-gray-700 dark:bg-gray-800 dark:border-gray-700 dark:text-gray-400 dark:hover:bg-gray-700 dark:hover:text-white">100</a>
                            </li>
                            <li>
                                <a href="#"
                                    class="block py-2 px-3 leading-tight text-gray-500 bg-white rounded-r-lg border border-gray-300 hover:bg-gray-100 hover:text-gray-700 dark:bg-gray-800 dark:border-gray-700 dark:text-gray-400 dark:hover:bg-gray-700 dark:hover:text-white">
                                    <span class="sr-only">Next</span>
                                    <svg class="w-5 h-5" aria-hidden="true" fill="currentColor" viewBox="0 0 20 20"
                                        xmlns="http://www.w3.org/2000/svg">
                                        <path fill-rule="evenodd"
                                            d="M7.293 14.707a1 1 0 010-1.414L10.586 10 7.293 6.707a1 1 0 011.414-1.414l4 4a1 1 0 010 1.414l-4 4a1 1 0 01-1.414 0z"
                                            clip-rule="evenodd"></path>
                                    </svg>
                                </a>
                            </li>
                        </ul>
                    </nav>
                </div>
            </div>
        </section>
    </div>
</template>

<script>
import Header from "@/components/header.vue";
import axios from "axios";
export default {
    components: {
        Header
    },
    data() {
        return {
            agents: "",
            agent_teams: "",
            team_selected: ''

        }

    },
    async mounted() {
        this.agent_info()
        this.teams_data()
    },

    methods: {
        agent_info() {
            axios.get('http://localhost/Php_Database_callCenter/agents_invitation.php', { params: {  }})
                .then(response => {

                    this.agents = response.data

                })
                .catch(function (error) {
                    // handle error
                });
        },
        teams_data() {
            axios.get('http://localhost/Php_Database_callCenter/teams_data.php')
                .then(response => {

                    this.agent_teams = response.data

                })
                .catch(function (error) {
                    // handle error
                });

        }


    }

}

</script>