<template>
    <div class="card">
        <img v-if="imageId" :src="getPosterUrl" />
        <div class="card-header">
            <h3>{{ title }}</h3>
            <div class="card-subheader">
                <h5>Directed by {{ director }}</h5>
                <h5>{{ releaseDate?.split("-")[0] }}</h5>
            </div>
            <p>{{ openingCrawl }}</p>
            <div class="card-details">
                <div class="card-info">
                    <h5>Characters</h5>
                    <h4>{{ totalCharacters }}</h4>
                </div>
                <div class="card-info">
                    <h5>Planets</h5>
                    <h4>{{ totalPlanets }}</h4>
                </div>
                <div class="card-info">
                    <h5>Starships</h5>
                    <h4>{{ totalStarships }}</h4>
                </div>
                <div class="card-info">
                    <h5>Vehicles</h5>
                    <h4>{{ totalVehicles }}</h4>
                </div>
                <div class="card-info">
                    <h5>Species</h5>
                    <h4>{{ totalSpecies }}</h4>
                </div>
            </div>
        </div>
    </div>
</template>

<script setup>
import { computed } from 'vue'

const props = defineProps({
    imageId: {
        type: [Number, String],
        required: true
    },
    title: {
        type: String,
        required: true
    },
    director: {
        type: String,
        required: true
    },
    releaseDate: {
        type: [Date, String],
        required: true
    },
    openingCrawl: {
        type: String,
        required: true
    },
    totalCharacters: {
        type: Number,
        required: true
    },
    totalPlanets: {
        type: Number,
        required: true
    },
    totalStarships: {
        type: Number,
        required: true
    },
    totalVehicles: {
        type: Number,
        required: true
    },
    totalSpecies: {
        type: Number,
        required: true
    },
})

const getPosterUrl = computed(() => {
    return `https://starwars-visualguide.com/assets/img/films/${props.imageId}.jpg`
})
</script>

<style scoped>
.card {
    background-color: rgba(255, 255, 255, .015);
    box-shadow:
        0 2px 6px rgba(0, 0, 0, 0.05),
        0 8px 16px rgba(0, 0, 0, 0.1),
        0 0 0 1px rgba(255, 255, 255, 0.1);
    padding: 16px;
    border-radius: 16px;
    transition: box-shadow .25s;
}
.card:hover {
    box-shadow:
        0 3px 6px rgba(0, 0, 0, 0.04),
        0 8px 16px rgba(0, 0, 0, 0.4),
        0 0 0 1px rgba(255, 255, 255, 0.4);
}

.card img {
    width: 100%;
    border-radius: 8px;
    box-shadow:
        0 2px 6px rgba(0, 0, 0, 0.05),
        0 8px 16px rgba(0, 0, 0, 0.1),
        0 0 0 1px rgba(255, 255, 255, 0.1);
}

.card-header {
    margin-top: 12px;
}
.card-subheader {
    margin-top: 8px;
    display: flex;
    align-content: center;
    justify-content: space-between;
    align-items: center;
    color: #a0a0a0;
}

p {
    font-size: 12px;
    line-height: 18px;
}

.card-details {
    margin-top: 24px;
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(100px, 1fr));
    gap: 12px;
}
.card-info {
    display: flex;
    flex-direction: column;
    align-content: center;
    justify-content: center;
    align-items: center;
    margin-bottom: 4px;
}
.card-info h5 {
    margin-bottom: 4px;
}
</style>