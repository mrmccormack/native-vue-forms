<template>
  <Page class="page">
    <ActionBar>
      <StackLayout orientation="horizontal">
        <Image
          src="https://cdn0.iconfinder.com/data/icons/pinpoint-interface/48/forms-512.png"
          width="32"
          height="32"
          verticalAlignment="center"
        />
        <Label text=" {N} and Vue.js: Forms" fontSize="16" verticalAlignment="center"/>
      </StackLayout>
    </ActionBar>

    <StackLayout>
      <Image src="https://i.stack.imgur.com/tFtk8.png?s=32&g=1" stretch="none"/>
      <RadDataForm :source="employees" :metadata="metadata"/>
    </StackLayout>
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
        notes: "hello notes",
        phoneNumber: "408-123-4567",
        emailAddress: "fredsmith234@gmail.com",
        owned: true
      },

      metadata: {
        isReadOnly: false,
        propertyAnnotations: [
          {
            name: "userId",
            index: 0,
            readOnly: true,
            displayName: "User Idxx:",
            hintText: "hint text here"
          },
          {
            name: "jobTitleName",
            index: 1
          },
          {
            name: "firstName",
            index: 2
          },
          {
            name: "lastName",
            index: 3
          },
          {
            name: "phoneNumber",
            index: 5,
            editor: "Number",
            validators: [
              {
                name: "Phone",
                params: {
                  errorMessage: "Please xxx phone."
                }
              }
            ]
          },
          {
            name: "emailAddress",
            index: 4,
            validators: [
              {
                name: "Email",
                params: {
                  errorMessage: "Please provide your @telerik.com email."
                }
              }
            ]
          },
          {
            name: "city",
            index: 6,
            editor: "Picker",
            valuesProvider: ["New York", "Washington", "Los Angeles"]
          },
          {
            name: "notes",
            index: 7,
            editor: "MultilineText"
          }
        ]
      }
    };
  }
};
</script>