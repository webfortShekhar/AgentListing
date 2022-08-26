<template>
    <div class="h-screen w-screen bg-slate-200 dark:bg-gray-800 overflow-hidden">
    <!-- <Skeleton v-if="callslogs"></Skeleton> -->
        <Header />
        <div class="p-0 mt-16 w-full h-[calc(100vh_-_64px)]  grid grid-cols-4 gap-3">
            <!-- Dialer Column -->
            <div class="rounded-0 bg-white dark:bg-gray-800 col-span-1">
             <Dialer /></div>

            <!-- Calls Log & Agent Activity Column -->
            <div
                class="rounded-0 bg-white dark:bg-gray-800 col-span-3 grid grid-cols-3 2xl:grid-cols-4 gap-3">
                <!-- Calls Log -->
                <div class="col-span-2 2xl:col-span-3">
                    <Callslogs />
                </div>
                <div class="col-span-1">
                    <AgentStatus />
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import Header from "@/components/header.vue";
import Callslogs from "@/components/CallsLog.vue";
import AgentStatus from "@/components/AgentStatus.vue";
import Dialer from "@/components/Dialer.vue";
import Skeleton from "@/components/Skeleton.vue";

export default {
    components: {
    Header,
    Callslogs,
    Dialer,
    AgentStatus,
    Skeleton
}
}
</script>