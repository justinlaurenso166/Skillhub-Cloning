<template>
    <div>
        <header>
            <div class="flex justify-between gap-10 items-center py-8 px-4">
                <div class="logo">
                    <NuxtLink>
                        <img src="@/assets/logo.png">
                    </NuxtLink>
                </div>
                <div class="flex gap-14 text-lg font-light">
                    <div class="nav-link hover:text-[#3fba96]">
                        <NuxtLink to="#">
                            About Us
                        </NuxtLink>
                    </div>
                    <div class="nav-link hover:text-[#3fba96]">
                        <NuxtLink to="#">
                            Courses
                        </NuxtLink>
                    </div>
                    <div class="nav-link hover:text-[#3fba96]">
                        <NuxtLink to="#">
                            Resources
                        </NuxtLink>
                    </div>
                    <div class="nav-link hover:text-[#3fba96]">
                        <NuxtLink to="#">
                            Online Learning
                        </NuxtLink>
                    </div>
                </div>
                <div>
                    <button class="tracking-wide text-white bg-[#3fba96] px-7 py-3 text-lg rounded-md font-light border border-white hover:bg-white hover:border hover:border-[#3fba96] hover:text-[#3fba96]">
                        Log In
                    </button>
                </div>
            </div>
        </header>
    </div>
</template>