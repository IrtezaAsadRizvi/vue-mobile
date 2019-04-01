<template>
    <div id="test">
        <task-bar viewName="Settings" @backButtonPressed="test()" :enableFixedOnTop="true">yup</task-bar>
        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Sit amet volutpat consequat mauris nunc congue. Facilisi morbi tempus iaculis urna id. Est placerat in egestas erat. Facilisis leo vel fringilla est ullamcorper. Turpis egestas pretium aenean pharetra magna ac placerat vestibulum lectus. Id faucibus nisl tincidunt eget nullam non nisi. Mauris sit amet massa vitae tortor condimentum lacinia. Tempus quam pellentesque nec nam aliquam. Consequat id porta nibh venenatis cras sed felis. Phasellus faucibus scelerisque eleifend donec pretium vulputate sapien nec sagittis. Est sit amet facilisis magna. Vel elit scelerisque mauris pellentesque pulvinar pellentesque. Neque convallis a cras semper auctor neque vitae tempus. Facilisis gravida neque convallis a cras semper.

            Pellentesque massa placerat duis ultricies lacus sed turpis tincidunt id. Amet luctus venenatis lectus magna fringilla urna porttitor rhoncus. Rhoncus urna neque viverra justo nec ultrices dui. Vitae semper quis lectus nulla at volutpat. Leo duis ut diam quam. Pretium viverra suspendisse potenti nullam. Ridiculus mus mauris vitae ultricies leo integer. Fames ac turpis egestas maecenas pharetra convallis. At lectus urna duis convallis convallis. A erat nam at lectus urna. Imperdiet nulla malesuada pellentesque elit eget gravida. Ut porttitor leo a diam sollicitudin tempor. Proin sagittis nisl rhoncus mattis rhoncus urna neque viverra. Id donec ultrices tincidunt arcu non. Pharetra massa massa ultricies mi. Maecenas accumsan lacus vel facilisis volutpat est. Interdum posuere lorem ipsum dolor sit amet consectetur adipiscing elit. Ut pharetra sit amet aliquam id diam. Arcu bibendum at varius vel pharetra vel. At augue eget arcu dictum varius.

            Commodo ullamcorper a lacus vestibulum sed arcu non odio. Leo duis ut diam quam nulla porttitor massa. Sapien et ligula ullamcorper malesuada proin libero nunc consequat. Tristique senectus et netus et. Leo urna molestie at elementum eu facilisis. Ut tellus elementum sagittis vitae. Sed viverra ipsum nunc aliquet bibendum enim facilisis gravida neque. Vulputate eu scelerisque felis imperdiet proin fermentum leo vel orci. Ipsum a arcu cursus vitae congue mauris rhoncus aenean. Lorem ipsum dolor sit amet. Quis auctor elit sed vulputate mi. Mi bibendum neque egestas congue quisque egestas diam in arcu. Erat nam at lectus urna duis convallis convallis. Quis auctor elit sed vulputate mi sit amet mauris commodo. Quis blandit turpis cursus in hac habitasse platea dictumst. Mus mauris vitae ultricies leo integer malesuada. Vitae ultricies leo integer malesuada nunc.

            Eleifend quam adipiscing vitae proin sagittis nisl rhoncus mattis. Adipiscing elit duis tristique sollicitudin nibh. Faucibus a pellentesque sit amet porttitor eget dolor morbi. Faucibus pulvinar elementum integer enim neque volutpat. Fames ac turpis egestas sed tempus urna et pharetra. Nec feugiat in fermentum posuere urna nec tincidunt praesent semper. Nulla at volutpat diam ut venenatis. Vulputate ut pharetra sit amet aliquam id diam maecenas. Faucibus pulvinar elementum integer enim. Lobortis elementum nibh tellus molestie. Quis blandit turpis cursus in hac habitasse platea. Lorem dolor sed viverra ipsum. Amet commodo nulla facilisi nullam vehicula ipsum a. Vitae semper quis lectus nulla at volutpat diam ut. Quis auctor elit sed vulputate mi sit amet mauris commodo. Ut venenatis tellus in metus vulputate eu. Vel risus commodo viverra maecenas accumsan.

            Nisi vitae suscipit tellus mauris a diam maecenas sed enim. Magna ac placerat vestibulum lectus. Sit amet cursus sit amet. Amet mattis vulputate enim nulla. Amet cursus sit amet dictum sit amet justo. Dictum at tempor commodo ullamcorper a. Vitae tempus quam pellentesque nec. Orci porta non pulvinar neque laoreet suspendisse interdum consectetur libero. Etiam non quam lacus suspendisse faucibus interdum posuere lorem ipsum. Sit amet nisl purus in mollis nunc. Id consectetur purus ut faucibus pulvinar elementum integer enim. Cum sociis natoque penatibus et. Nec nam aliquam sem et tortor consequat id porta. Eu facilisis sed odio morbi quis commodo odio. In arcu cursus euismod quis viverra nibh cras. Suspendisse in est ante in nibh. Morbi enim nunc faucibus a pellentesque. Nibh venenatis cras sed felis. Tincidunt dui ut ornare lectus sit amet.</p>
    </div>
</template>

<script>
    export default {
        name: "test",
        components: {
            'nice-handsome-button': () => import('./NiceHandsomeButton'),
            'task-bar': () => import('./components/layout/Taskbar'),
        },
        mounted() {
            var viewPortTag=document.createElement('meta');
            viewPortTag.id="viewport";
            viewPortTag.name = "viewport";
            viewPortTag.content = "width=device-width, initial-scale=1.0; maximum-scale=1.0; user-scalable=0;";
            document.getElementsByTagName('head')[0].appendChild(viewPortTag);
        },
        methods: {
            test() {
                console.log('test: working!')
            }
        }
    }
</script>

<style>
    html, body {
        padding: 0;
        margin: 0;
    }
</style>