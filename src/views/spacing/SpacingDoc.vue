<template>
	<AppDoc name="SpacingDemo" :sources="sources" github="spacing/SpacingDemo.vue" >
        <h5>Getting Started</h5>
        <p>The spacing classes use the <i>{property}{position}-{value}</i> syntax whereas for responsive
        values <i>{breakpoint}:{property}{position}-{value}</i> format is used.</p>

        <h5>Property</h5>
        <p>Property can either be a margin or a padding.</p>
        <ul>
            <li><b>m</b>: margin</li>
            <li><b>p</b>: padding</li>
        </ul>

        <h5>Position</h5>
        <p>Position are available for the individual sides, the x-y axis or blank for the shortand of all sides.</p>
        <ul>
            <li><b>t</b>: top</li>
            <li><b>b</b>: bottom</li>
            <li><b>l</b>: left</li>
            <li><b>r</b>: right</li>
            <li><b>x</b>: left and right</li>
            <li><b>y</b>: top and bottom</li>
            <li><b>blank</b>: all sides</li>
        </ul>

        <h5>Value</h5>
        <p>Value field varies from 0 to 6 where default value of the <i>$spacer</i> is 1rem. The special <i>auto</i> value is available to margins only and used to center elements.</p>
        <ul>
            <li><b>0</b>: $spacer * 0</li>
            <li><b>1</b>: $spacer * .25</li>
            <li><b>2</b>: $spacer * .5</li>
            <li><b>3</b>: $spacer * 1</li>
            <li><b>4</b>: $spacer * 1.5</li>
            <li><b>5</b>: $spacer * 2</li>
            <li><b>6</b>: $spacer * 3</li>
            <li><b>7</b>: $spacer * 4</li>
            <li><b>8</b>: $spacer * 5</li>
            <li><b>auto</b>: auto margin</li>
        </ul>

        <h5>Breakpoint</h5>
        <p>Breakpoints define how the spacing should be defined depending on the screen size. Design is mobile first so smaller values
            can also apply to larger values e.g. md also applies to lg or xl if they are not explicitly defined.</p>
        <ul>
            <li><b>sm</b>: small screens e.g. phones</li>
            <li><b>md</b>: medium screens e.g. tablets</li>
            <li><b>lg</b>: large screens e.g. notebooks</li>
            <li><b>xl</b>: larger screens .e.g monitors</li>
        </ul>

        <h5>Examples</h5>
<pre v-code><code>
&lt;div class="mb-2"&gt;Margin bottom with level 2&lt;/div&gt;
&lt;div class="mt-4"&gt;Margin top with level 2&lt;/div&gt;
&lt;div class="m-2"&gt;Margin for all sides with level 2&lt;/div&gt;
&lt;div class="mx-auto"&gt;Auto margins for left and right side&lt;/div&gt;
&lt;div class="pb-4"&gt;Padding bottom with level 4&lt;/div&gt;
&lt;div class="p-1"&gt;Padding for all sides with level 1&lt;/div&gt;
&lt;div class="m-1 p-1 lg:m-3"&gt;Level 3 spacing for lg screens and level 1 for smaller screens (xs).&lt;/div&gt;

</code></pre>

        <h5>Customization</h5>
        <p>A custom build with different values can be obtained from <a href="https://github.com/primefaces/primeflex">PrimeFlex</a> using the _variables.scss file.</p>

        <h5>Dependencies</h5>
        <p>PrimeFlex 3.1.2.</p>
    </AppDoc>
</template>

<script>
export default {
    data() {
        return {
            sources: {
                'options-api': {
					tabName: 'Options API Source',
					content: `
<template>
    <div>
        <div class="card">
            <h5>Margin</h5>
            <h6>Without Spacing</h6>
            <Button type="button" label="Button 1" style="width:20rem" />
            <Button type="button" label="Button 2" style="width:20rem" />

            <h6>With Spacing</h6>
            <Button type="button" label="Button 1" style="width:20rem" class="mr-2 mb-2" />
            <Button type="button" label="Button 2" style="width:20rem" class="mb-2"/>

            <h5>Responsive Margin</h5>
            <h6>Without Spacing</h6>
            <div class="grid formgrid p-fluid">
                <div class="col-12 lg:col-4">
                    <InputText />
                </div>
                <div class="col-12 lg:col-4">
                    <InputText />
                </div>
                <div class="col-12 lg:col-4">
                    <InputText />
                </div>
            </div>

            <h6>With Spacing</h6>
            <div class="grid formgrid p-fluid">
                <div class="col-12 mb-2 lg:col-4 lg:mb-0">
                    <InputText />
                </div>
                <div class="col-12 mb-2 lg:col-4 lg:mb-0">
                    <InputText />
                </div>
                <div class="col-12 mb-2 lg:col-4 lg:mb-0">
                    <InputText />
                </div>
            </div>

            <h6>Center</h6>
            <div class="demo-container p-4">
                <Button type="button" label="Button" class="block mx-auto" />
            </div>
        </div>

        <div class="card">
            <h5>Padding</h5>
            <h6>Without Spacing</h6>
            <div class="demo-container">
                <Button type="button" label="Button" />
            </div>

            <h6>With Spacing</h6>
            <div class="demo-container p-3">
                <Button type="button" label="Button" />
            </div>

            <h6>Responsive Spacing</h6>
            <div class="demo-container p-0 sm:col-1 md:col-2 lg:col-3">
                <Button type="button" label="Button" />
            </div>
        </div>
    </div>    
</template>

<script>
export default {

}
<\\/script>

<style scoped>
.demo-container {
    border: 1px solid var(--surface-d);
}
</style>
`
				},
                'composition-api': {
					tabName: 'Composition API Source',
					content: `
<template>
    <div>
        <div class="card">
            <h5>Margin</h5>
            <h6>Without Spacing</h6>
            <Button type="button" label="Button 1" style="width:20rem" />
            <Button type="button" label="Button 2" style="width:20rem" />

            <h6>With Spacing</h6>
            <Button type="button" label="Button 1" style="width:20rem" class="mr-2 mb-2" />
            <Button type="button" label="Button 2" style="width:20rem" class="mb-2"/>

            <h5>Responsive Margin</h5>
            <h6>Without Spacing</h6>
            <div class="grid formgrid p-fluid">
                <div class="col-12 lg:col-4">
                    <InputText />
                </div>
                <div class="col-12 lg:col-4">
                    <InputText />
                </div>
                <div class="col-12 lg:col-4">
                    <InputText />
                </div>
            </div>

            <h6>With Spacing</h6>
            <div class="grid formgrid p-fluid">
                <div class="col-12 mb-2 lg:col-4 lg:mb-0">
                    <InputText />
                </div>
                <div class="col-12 mb-2 lg:col-4 lg:mb-0">
                    <InputText />
                </div>
                <div class="col-12 mb-2 lg:col-4 lg:mb-0">
                    <InputText />
                </div>
            </div>

            <h6>Center</h6>
            <div class="demo-container p-4">
                <Button type="button" label="Button" class="block mx-auto" />
            </div>
        </div>

        <div class="card">
            <h5>Padding</h5>
            <h6>Without Spacing</h6>
            <div class="demo-container">
                <Button type="button" label="Button" />
            </div>

            <h6>With Spacing</h6>
            <div class="demo-container p-3">
                <Button type="button" label="Button" />
            </div>

            <h6>Responsive Spacing</h6>
            <div class="demo-container p-0 sm:col-1 md:col-2 lg:col-3">
                <Button type="button" label="Button" />
            </div>
        </div>
    </div>    
</template>

<script>
export default {

}
<\\/script>

<style scoped>
.demo-container {
    border: 1px solid var(--surface-d);
}
</style>
`
				},
                'browser-source': {
					tabName: 'Browser Source',
					content: `<div id="app">
            <div class="card">
                <h5>Margin</h5>
                <h6>Without Spacing</h6>
                <p-button type="button" label="Button 1" style="width:20rem"></p-button>
                <p-button type="button" label="Button 2" style="width:20rem"></p-button>

                <h6>With Spacing</h6>
                <p-button type="button" label="Button 1" style="width:20rem" class="mr-2 mb-2"></p-button>
                <p-button type="button" label="Button 2" style="width:20rem" class="mb-2"></p-button>

                <h5>Responsive Margin</h5>
                <h6>Without Spacing</h6>
                <div class="grid formgrid p-fluid">
                    <div class="col-12 lg:col-4">
                        <p-inputtext></p-inputtext>
                    </div>
                    <div class="col-12 lg:col-4">
                        <p-inputtext></p-inputtext>
                    </div>
                    <div class="col-12 lg:col-4">
                        <p-inputtext></p-inputtext>
                    </div>
                </div>

                <h6>With Spacing</h6>
                <div class="grid formgrid p-fluid">
                    <div class="col-12 mb-2 lg:col-4 lg:mb-0">
                        <p-inputtext></p-inputtext>
                    </div>
                    <div class="col-12 mb-2 lg:col-4 lg:mb-0">
                        <p-inputtext></p-inputtext>
                    </div>
                    <div class="col-12 mb-2 lg:col-4 lg:mb-0">
                        <p-inputtext></p-inputtext>
                    </div>
                </div>

                <h6>Center</h6>
                <div class="demo-container p-4">
                    <p-button type="button" label="Button" class="block mx-auto"></p-button>
                </div>
            </div>

            <div class="card">
                <h5>Padding</h5>
                <h6>Without Spacing</h6>
                <div class="demo-container">
                    <p-button type="button" label="Button"></p-button>
                </div>

                <h6>With Spacing</h6>
                <div class="demo-container p-3">
                    <p-button type="button" label="Button"></p-button>
                </div>

                <h6>Responsive Spacing</h6>
                <div class="demo-container p-0 sm:col-1 md:col-2 lg:col-3">
                    <p-button type="button" label="Button"></p-button>
                </div>
            </div>
        </div>    

        <script type="module">
        const { createApp } = Vue;

        const App = {
            components: {
                "p-inputtext": primevue.inputtext,
                "p-button": primevue.button
            }
        };

        createApp(App)
            .use(primevue.config.default)
            .mount("#app");
        <\\/script>

        <style>
        .demo-container {
            border: 1px solid var(--surface-d);
        }
        </style>
`
				}
            }
        }
    }
}
</script>
