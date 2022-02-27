<template>
    <div class="users">
        <ul>
            <li
                v-for="(user, index) in users"
                :key="user.id"
                :class="cssStyle(index, user.selected, user.activated)"
                @click="toggleActivated(index)"
                @mouseover="toggleMouseOver(index)"
                @mouseout="toggleMouseOut(index)"
            >
                {{ user.name }}
            </li>
        </ul>
        <div>Selecionados: {{ sortAndGetUsersActivateds }}</div>
    </div>
</template>

<script>
export default {
    name: 'CssDinamicD',
    data() {
        return {
            users: [],
            usersActivateds: [],
        };
    },
    mounted() {
        this.populate();
        this.activate();
    },
    methods: {
        populate() {
            const users = [
                { id: 100, name: 'Tiago', selected: false, activated: false },
                { id: 200, name: 'Sandro', selected: false, activated: true },
                { id: 300, name: 'Marcos', selected: false, activated: false },
            ];

            this.users = users;
        },
        activate() {
            this.users.forEach(({ id, activated }) => {
                if (activated) {
                    this.usersActivateds.push(id);
                }
            });
        },
        toggleMouseOver(index) {
            this.users[index].selected = !this.users[index].selected;
        },
        toggleMouseOut(index) {
            this.users[index].selected = !this.users[index].selected;
        },
        toggleActivated(index) {
            this.users[index].activated = !this.users[index].activated;

            const userId = this.users[index].id;

            const findIndexId = this.usersActivateds.findIndex((id) => id === userId);

            if (findIndexId === -1) {
                this.usersActivateds.push(userId);
            } else {
                this.usersActivateds.splice(findIndexId, 1);
            }
        },
    },
    computed: {
        sortAndGetUsersActivateds() {
            return this.usersActivateds.sort((a, b) => a - b);
        },
        cssStyle() {
            return (index, selected, activated) => {
                return {
                    c0: true,
                    c1: index % 2 === 0 ? true : false,
                    c2: selected ? true : false,
                    c3: activated ? true : false,
                };
            };
        },
    },
};
</script>
<style>
* {
    font-family: arial;
}
.box,
.users ul li {
    cursor: pointer;
}
.demo {
    display: flex;
    width: 100px;
    height: 100px;
    background-color: #eee;
}
.rotate {
    transform: rotate(45deg);
}
.restartRotate {
    transform: rotate(0deg);
}
.c0 {
    background-color: #eee;
}
.c1 {
    background-color: #ccc;
}
.c2 {
    background-color: aquamarine !important;
}
.c3 {
    background-color: cornflowerblue;
}
</style>
