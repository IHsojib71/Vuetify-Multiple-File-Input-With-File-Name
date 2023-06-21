<template>
    <div>
        <v-file-input  v-model="myfile" 
                            :prepend-icon="null" 
                            counter 
                            dense 
                            label="Select Files" 
                            outlined
                            prepend-inner-icon="mdi-paperclip" show-size multiple>
                            <template v-slot:selection="{ text, index, file }">
                                <v-chip small text-color="white" color="primary" close @click:close="removePhotoID(index)">
                                    {{ text }}
                                </v-chip>
                            </template>
         </v-file-input>

    </div>
</template>

<script>
export default {
    props:{
        
    },
    data() {
        return {
            myfile : []
        }
    },
   
    methods:{
        removePhotoID(index) {
        this.myfile.splice(index, 1);
        },
    }

};
</script>