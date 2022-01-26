<script>
import PrimaryButton from './PrimaryButton.vue';
// import ToggleInput from './ToggleInput.vue';
import contacts from '../../contacts.json';

export default {
  props: ['tag'],
  components: { PrimaryButton },
  data() {
    return {
      toggled: true,
      contacts,
    };
  },

  render(createElement) {
    //   return this.$scopedSlots.default({
    //       subject: 'universe'
    //   })

      return createElement('span', {
          attrs: {
              class: 'text-xl text-blue font-bold'
          }
      }, [
        //   this.$slots.default
        this.$scopedSlots.default({
            subject: 'universe'
        })
      ]
      )
  }

//   render(createElement) {
//     return createElement('div', {}, [
//       createElement('h1', {}, 'Your contacts'),
//       createElement(
//         'ul',
//         {},
//         this.contacts.map((contact) => {
//           return createElement(
//             'li',
//             {},
//             `${contact.name.first} ${contact.name.last}`
//           );
//         })
//       ),
//     ]);
//   },

  //   render(createElement) {
  //       return createElement(ToggleInput, {
  //           props: {
  //               value: this.toggled,
  //           },
  //           on: {
  //             input: (newValue) => this.toggled = newValue
  //           }
  //       });
  //   }

  // render(createElement) {
  //     return createElement(this.tag, {
  //         attrs: {
  //             class: 'btn btn-blue'
  //         },
  //         on: {
  //             click(){
  //                 alert('Clicked!')
  //             }
  //         },
  //     }, 'Hello World')
  // }

  //   render(createElement) {
  //     return createElement(
  //       PrimaryButton,
  //       {
  //         nativeOn: {
  //           click: () => alert('Clicked!'),
  //         },
  //       },
  //       'Hello World'
  //     );
  //   },
};
</script>

<style></style>
