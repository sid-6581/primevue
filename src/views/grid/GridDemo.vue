<template>
    <div>
        <div class="content-section introduction">
            <AppDemoActions />
        </div>

        <div class="content-section implementation flexgrid-demo">
            <h1>Grid System</h1>
            <p>Grid is a lightweight flex based responsive layout utility optimized for mobile phones, tablets and desktops.</p>

            <h5>Basic</h5>
            <div class="grid">
                <div class="col">
                    <div class="box">1</div>
                </div>
                <div class="col">
                    <div class="box">2</div>
                </div>
                <div class="col">
                    <div class="box">3</div>
                </div>
            </div>

            <h5>Dynamic</h5>
            <Button type="button" icon="pi pi-plus" title="Add Column" @click="addColumn" :disabled="columns.length === 20" style="margin-right: .5em" />
            <Button type="button" icon="pi pi-minus" title="Remove Column" @click="removeColumn" :disabled="columns.length === 1" />

            <div style="margin-top: .5em">
                <transition-group name="dynamic-box" tag="div" class="grid">
                    <div v-for="col of columns" :key="col" class="col">
                        <div class="box">{{col}}</div>
                    </div>
                </transition-group>
            </div>

            <h5>Reverse Direction</h5>
            <div class="grid flex-row-reverse">
                <div class="col">
                    <div class="box">1</div>
                </div>
                <div class="col">
                    <div class="box">2</div>
                </div>
                <div class="col">
                    <div class="box">3</div>
                </div>
            </div>

            <h5>Column Direction</h5>
            <div class="grid flex-column">
                <div class="col">
                    <div class="box">1</div>
                </div>
                <div class="col">
                    <div class="box">2</div>
                </div>
                <div class="col">
                    <div class="box">3</div>
                </div>
            </div>

            <h5>Reverse Column Direction</h5>
            <div class="grid flex-column-reverse">
                <div class="col">
                    <div class="box">1</div>
                </div>
                <div class="col">
                    <div class="box">2</div>
                </div>
                <div class="col">
                    <div class="box">3</div>
                </div>
            </div>

            <h5>12 Column Grid</h5>
            <div class="grid">
                <div class="col-4">
                    <div class="box">4</div>
                </div>
                <div class="col">
                    <div class="box">1</div>
                </div>
                <div class="col">
                    <div class="box">1</div>
                </div>
                <div class="col">
                    <div class="box">1</div>
                </div>
                <div class="col">
                    <div class="box">1</div>
                </div>
                <div class="col">
                    <div class="box">1</div>
                </div>
                <div class="col">
                    <div class="box">1</div>
                </div>
                <div class="col">
                    <div class="box">1</div>
                </div>
                <div class="col">
                    <div class="box">1</div>
                </div>
            </div>

            <div class="grid">
                <div class="col-2">
                    <div class="box">2</div>
                </div>
                <div class="col-6">
                    <div class="box">6</div>
                </div>
                <div class="col-4">
                    <div class="box">4</div>
                </div>
            </div>

            <div class="grid">
                <div class="col-8">
                    <div class="box">8</div>
                </div>
                <div class="col-2">
                    <div class="box">2</div>
                </div>
                <div class="col-2">
                    <div class="box">2</div>
                </div>
            </div>

            <h5>MultiLine</h5>
            <div class="grid">
                <div class="col-6">
                    <div class="box">6</div>
                </div>
                <div class="col-6">
                    <div class="box">6</div>
                </div>
                <div class="col-6">
                    <div class="box">6</div>
                </div>
                <div class="col-6">
                    <div class="box">6</div>
                </div>
            </div>

            <h5>Fixed Width Column</h5>
            <div class="grid">
                <div class="col-fixed" style="width:100px">
                    <div class="box">100px</div>
                </div>
                <div class="col">
                    <div class="box">auto</div>
                </div>
            </div>

            <h5>Responsive</h5>
            <div class="grid">
                <div class="col-12 md:col-6 lg:col-3">
                    <div class="box">col-12 md:col-6 lg:col-3</div>
                </div>
                <div class="col-12 md:col-6 lg:col-3">
                    <div class="box">col-12 md:col-6 lg:col-3</div>
                </div>
                <div class="col-12 md:col-6 lg:col-3">
                    <div class="box">col-12 md:col-6 lg:col-3</div>
                </div>
                <div class="col-12 md:col-6 lg:col-3">
                    <div class="box">col-12 md:col-6 lg:col-3</div>
                </div>
            </div>

            <h5>Horizontal Alignment - Start</h5>
            <div class="grid justify-content-start">
                <div class="col-2">
                    <div class="box">2</div>
                </div>
                <div class="col-1">
                    <div class="box">1</div>
                </div>
                <div class="col-4">
                    <div class="box">4</div>
                </div>
            </div>

            <h5>Horizontal Alignment - End</h5>
            <div class="grid justify-content-end">
                <div class="col-2">
                    <div class="box">2</div>
                </div>
                <div class="col-1">
                    <div class="box">1</div>
                </div>
                <div class="col-4">
                    <div class="box">4</div>
                </div>
            </div>

            <h5>Horizontal Alignment - Center</h5>
            <div class="grid justify-content-center">
                <div class="col-2">
                    <div class="box">2</div>
                </div>
                <div class="col-1">
                    <div class="box">1</div>
                </div>
                <div class="col-4">
                    <div class="box">4</div>
                </div>
            </div>

            <h5>Horizontal Alignment - Between</h5>
            <div class="grid justify-content-center">
                <div class="col-2">
                    <div class="box">2</div>
                </div>
                <div class="col-1">
                    <div class="box">1</div>
                </div>
                <div class="col-4">
                    <div class="box">4</div>
                </div>
            </div>

            <h5>Horizontal Alignment - Around</h5>
            <div class="grid justify-content-around">
                <div class="col-2">
                    <div class="box">2</div>
                </div>
                <div class="col-1">
                    <div class="box">1</div>
                </div>
                <div class="col-4">
                    <div class="box">4</div>
                </div>
            </div>

            <h5>Horizontal Alignment - Even</h5>
            <div class="grid justify-content-evenly">
                <div class="col-2">
                    <div class="box">2</div>
                </div>
                <div class="col-1">
                    <div class="box">1</div>
                </div>
                <div class="col-4">
                    <div class="box">4</div>
                </div>
            </div>

            <h5>Vertical Alignment - Start</h5>
            <div class="grid align-items-start vertical-container">
                <div class="col">
                    <div class="box">4</div>
                </div>
                <div class="col">
                    <div class="box">4</div>
                </div>
                <div class="col">
                    <div class="box">4</div>
                </div>
            </div>

            <h5>Vertical Alignment - End</h5>
            <div class="grid align-items-end vertical-container">
                <div class="col">
                    <div class="box">4</div>
                </div>
                <div class="col">
                    <div class="box">4</div>
                </div>
                <div class="col">
                    <div class="box">4</div>
                </div>
            </div>

            <h5>Vertical Alignment - Center</h5>
            <div class="grid align-items-center vertical-container">
                <div class="col">
                    <div class="box">4</div>
                </div>
                <div class="col">
                    <div class="box">4</div>
                </div>
                <div class="col">
                    <div class="box">4</div>
                </div>
            </div>

            <h5>Vertical Alignment - Stretch</h5>
            <div class="grid align-items-stretch vertical-container">
                <div class="col">
                    <div class="box box-stretched">4</div>
                </div>
                <div class="col">
                    <div class="box box-stretched">4</div>
                </div>
                <div class="col">
                    <div class="box box-stretched">4</div>
                </div>
            </div>

            <h5>Vertical Alignment - Per Column</h5>
            <div class="grid vertical-container">
                <div class="col align-self-start">
                    <div class="box">4</div>
                </div>
                <div class="col align-self-center">
                    <div class="box">4</div>
                </div>
                <div class="col align-self-end">
                    <div class="box">4</div>
                </div>
            </div>

            <h5>Offset</h5>
            <div class="grid">
                <div class="col-6 col-offset-3">
                    <div class="box">6</div>
                </div>
            </div>

            <div class="grid">
                <div class="col-4">
                    <div class="box">4</div>
                </div>
                <div class="col-4 col-offset-4">
                    <div class="box">4</div>
                </div>
            </div>

            <h5>Nested</h5>
            <div class="grid nested-grid">
                <div class="col-8">
                    <div class="grid">
                        <div class="col-6">
                            <div class="box">6</div>
                        </div>
                        <div class="col-6">
                            <div class="box">6</div>
                        </div>
                        <div class="col-12">
                            <div class="box">12</div>
                        </div>
                    </div>
                </div>
                <div class="col-4">
                    <div class="box box-stretched">4</div>
                </div>
            </div>

            <h5>Panels</h5>
            <div class="grid">
                <div class="col">
                    <Panel header="Header">
                        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                        Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
                        Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat
                        cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</p>
                    </Panel>
                </div>
                <div class="col">
                    <Panel header="Header">
                        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                        Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
                        Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat
                        cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</p>
                    </Panel>
                </div>
                <div class="col">
                    <Panel header="Header">
                        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                        Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
                        Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat
                        cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</p>
                    </Panel>
                </div>
            </div>
        </div>

        <GridDoc />
    </div>
</template>

<script>
import GridDoc from './GridDoc';

export default {
    data() {
        return {
            columns: [0, 1, 2, 3, 4, 5]
        }
    },
    methods: {
        addColumn() {
            this.columns = [...this.columns, this.columns.length];
        },
        removeColumn() {
            this.columns.pop();
        }
    },
    components: {
        'GridDoc': GridDoc
    }
}
</script>

<style lang="scss" scoped>
.flexgrid-demo {
    .box {
        background-color: var(--surface-e);
        text-align: center;
        padding-top: 1rem;
        padding-bottom: 1rem;
        border-radius: 4px;
        box-shadow: 0 2px 1px -1px rgba(0,0,0,.2), 0 1px 1px 0 rgba(0,0,0,.14), 0 1px 3px 0 rgba(0,0,0,.12);
    }

    .box-stretched {
        height: 100%;
    }

    .vertical-container {
        margin: 0;
        height: 200px;
        background: var(--surface-d);
        border-radius: 4px;
    }

    .nested-grid .col-4 {
        padding-bottom: 1rem;
    }

    .dynamic-box-enter-active, .dynamic-box-leave-active {
        transition: all .5s;
    }

    .dynamic-box-enter, .dynamic-box-leave-to {
        opacity: 0;
    }

    .dynamic-box-enter, .dynamic-box-leave-to {
        transform: translateX(30px);
    }

    p {
        margin: 0;
    }
}
</style>
