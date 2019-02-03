<template>
    <Page class="page">
        <ActionBar title="NativeScript/Vue.js - Forms" class="action-bar" />
        <RadDataForm :source="employees" :metadata="metadata" />
    </Page>
</template>

<script>
    /*
Ref : http://docs.telerik.com/devtools/nativescript-ui/Controls/NativeScript/DataForm/Validation/dataform-validation-overview#json-metadata

*/
    import Vue from "nativescript-vue";
    import RadDataForm from "nativescript-ui-dataform/vue";
    Vue.use(RadDataForm);

    export default {
        data() {
            return {
                employees: {
                    userId: "123",
                    jobTitleName: "Developer",
                    firstName: "Fred",
                    lastName: "Smith",
                    city: "",
                    phoneNumber: "408-123-4567",
                    emailAddress: "fredsmith234@gmail.com",
                    owned: true
                },

                metadata: {
                    isReadOnly: false,
                    propertyAnnotations: [{
                            name: "userId",
                            index: 0,
                            displayName: "User Id:",
                            hintText: "hint text here"
                        },
                        {
                            name: "jobTitleName",
                            index: 1
                        },
                        {
                            name: "firstName",
                            index: 2,
                            imageResource: "https://cdn3.iconfinder.com/data/icons/woothemesiconset/32/user.png"
                        },
                        {
                            name: "lastName",
                            index: 3
                        },
                        {
                            name: "phoneNumber",
                            index: 5
                        },
                        {
                            name: "emailAddress",
                            index: 4,
                            validators: [{
                                name: "Email",
                                params: {
                                    errorMessage: "Please provide your @telerik.com email."
                                }
                            }]
                        },
                        {
                            name: "city",
                            index: 6,
                            editor: "Picker",
                            valuesProvider: [
                                "New York",
                                "Washington",
                                "Los Angeles"
                            ]
                        }
                    ]
                }
            };
        }
    };
</script>