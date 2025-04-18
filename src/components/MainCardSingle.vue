<script setup>
    import { faker } from '@faker-js/faker'
    
    // const firstname = faker.person.firstName()
    // const lastname = faker.person.lastName()
    // const jobtitle = faker.person.jobTitle()
    // const bio = faker.lorem.lines(2)
    // const username = faker.internet.username({ firstName: firstname, lastName: lastname }).toLowerCase()


const props = defineProps({
    employee: {
        type: Object,
        required: true,
        default: () => {
            return {
                _id: "67fc3d3f1b6bfee383b87d00",
                userName: "beckmun",
                firstName: "Becky",
                lastName: "Muniz",
                title: "Marine Biology Student",
                quote: "Do or do not there is no try",
                __v: 0
               } 
            },
        },
    })
</script>

<template>
    <RouterLink :to="{name: 'CardDetail', params:{id: props.employee._id}}">
        <div class="border border-gray-500 rounded-lg shadow bg-gray-200 h-full">
            <img class="object-fill h-480 w-960 rounded-t-lg" v-bind:src="faker.image.urlLoremFlickr({category: 'cats', height:480, width:960})"/>
            <div class="p-4">
                <p class="mb-2 test-2xl font-bold">{{ props.employee.firstName }} {{ props.employee.lastName }}</p>
                <p class="mb-3 font-normal text-gray-800">{{ props.employee.title }}</p>
                <p class="mb-3 font-normal text-gray-800">{{ props.employee.quote }}</p>

            </div>
        </div>
    </RouterLink>


</template>