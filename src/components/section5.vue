<template>
    <section>
        <div class="text-start my-3 mx-4">
            <div class="btn-group" role="group" aria-label="Basic mixed styles example">
                <button @click="ToggleItalian()" type="button" class="btn btn-success">Italian</button>
                <button @click="ToggleSpanish()" type="button" class="btn btn-danger">Spanish</button>
                <button type="button" class="btn btn-primary">French</button>
            </div>
        </div>
        <ul class="text-start" v-for="(Sentence, index) in Sentences" :key="index">
            <p class="display-5 py-3">{{Sentence.SentEnglish}}</p>
            <p class="fw-lighter display-6 py-3" v-if="Spanish === true">{{Sentence.SentSpanish}}</p>
            <p v-if="Italian === true" class="fw-lighter display-6 py-3">{{ Sentence.SentItalian }}</p>
        </ul>
    </section> 
</template>

<script>
export default {
    data(){
        return{
            Sentences: [
                {
                    SentEnglish: 'Sentence in English', SentSpanish: 'Sentence in Spanish', SentItalian: 'Sentence in Italian', SentFrench: 'Sentence in French',
                },
                {
                    SentEnglish: 'Sentence 2 in English', SentSpanish: 'Sentence 2 in Spanish', SentItalian: 'Sentence 2 in Italian', SentFrench: 'Sentence 2 in French',
                },
            ],
            Spanish: false,
            Italian: false,
            Sentence:'',
        }
    },
    methods:{
        ToggleItalian(){
            this.Italian = !this.Italian
        },
        ToggleSpanish(){
            this.Spanish = !this.Spanish
        }     
    }
}
</script>