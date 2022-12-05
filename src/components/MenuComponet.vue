<template>
    <div class="card p-0 alert alert-light">
        <div class="card-header py-2 px-3">
            <h6 class="mb-0 text-dark">Menu Items</h6>
        </div>
        <div class="card-body py-2 px-3">
            <ul class="custom-scrollbar scrollable list-unstyled">
                <li class="text-capitalize" v-for="item in menu.nav_menu_items" :key="item.id">
                    <div class="menu-item alert alert-primary w-75 p-2 mb-1">
                        <h6 class="mb-0 d-inline">{{ item.label }}</h6>
                            <div class="d-inline mt-3  ml-4 text-right">
                                <a href=""><i class="bx bx-trash"></i></a>
                                <a href=""><i class="bx bx-edit"></i></a>
                            </div>
                    </div>
                    <ul class="children" style="list-style: georgian;" v-if="item.children">
                        <li class="child-menu-item" v-for="child in item.children" :key="child.id">
                            <div class="alert alert-success p-2 mb-1 w-75">
                                <h6 class="mb-0 d-inline">{{ child.label }}</h6>
                                <div class="d-inline mt-3  ml-4 text-right">
                                    <a href=""><i class="bx bx-trash"></i></a>
                                    <a href=""><i class="bx bx-edit"></i></a>
                                </div>
                            </div>
                            <ul class="children" style="list-style: georgian;" v-if="child.children">
                                <li class="child-menu-item" v-for="childChild in child.children" :key="childChild.id">
                                    <div class="alert alert-success p-2 mb-1 w-75">
                                        <h6 class="mb-0 d-inline">{{ childChild.label }}</h6>
                                        <div class="d-inline mt-3  ml-4 text-right">
                                            <a href=""><i class="bx bx-trash"></i></a>
                                            <a href=""><i class="bx bx-edit"></i></a>
                                        </div>
                                    </div>
                                </li>
                            </ul>
                        </li>
                    </ul>
                </li>
            </ul>
        </div>
    </div>
</template>
  
<script>
export default {
    name: 'MenuComponet',
    
    data(){
        return {
            menu: Object
        }
    },
    mounted() {
        fetch('http://localhost:3000/menu')
        .then(response => response.json())
        .then(data => this.menu = data)
        .catch(err => console.log(err.message))
    }

}
</script>
  
  <!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>


  