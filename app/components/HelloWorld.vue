<template>
    <Page class="page">
        <ActionBar title="JSON example" class="action-bar" />
        <RadDataForm :source="album" :metadata="metadata" />
    </Page>
</template>

<script>
    import Vue from "nativescript-vue";
    import RadDataForm from "nativescript-ui-dataform/vue";
    Vue.use(RadDataForm);

    export default {
        data() {
            return {
                album: {
                    bandName: "Beatles",
                    albumName: "Seargent Peppers",
                    year: "2017",
                    owned: true,
                    borrowed: true
                },
                metadata: {
                    "isReadOnly": false,
                    "propertyAnnotations": [{
                            "name": "bandName",
                            "index": 0,
                            "displayName": "Name of Band",
                            hintText: "hint text here"
                        },
                        {
                            "name": "albumName",
                            "index": 1
                        },
                        {
                            "name": "year",
                            "index": 2
                        },
                        {
                            "name": "owned",
                            "index": 4
                        },
                        {
                            "name": "myRating",
                            "index": 3
                        }
                    ]
                }
            };
        }
    };
</script>