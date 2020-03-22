<template>
    <div class="container text-center flex-column-center flex-grow">
        <div class="row justify-content-center flex-grow">
            <div class="col-md-8 flex-column-center">
                <div class="form-group text-center">
                    <p>Right now, I have</p>
                    <div class="row my-3">
                        <div class="col-4 text-right flex-column-center">
                            <div>
                                <button
                                    class="btn btn-outline-primary"
                                    @click="decreaseTimeSpan"
                                >-</button>
                            </div>
                        </div>
                        <div class="col-4 flex-column-center">
                            <div>{{ timeSpanList[selectedTimeSpan].text }}</div>
                        </div>
                        <div class="col-4 text-left flex-column-center">
                            <div>
                                <button
                                    class="btn btn-outline-primary"
                                    @click="increaseTimeSpan"
                                >+</button>
                            </div>
                        </div>
                    </div>
                    <button class="btn btn-primary btn-lg">
                        Give me something to do!
                    </button>
                </div>
            </div>
        </div>

        <div class="row justify-content-center">
            <div class="col-md-8">
                <button class="btn btn-primary btn-lg my-3">
                    + Add a task
                </button>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                selectedTimeSpan: 3,
                timeSpanList: [
                    {minutes: 5, text: "5 minutes"},
                    {minutes: 10, text: "10 minutes"},
                    {minutes: 30, text: "30 minutes"},
                    {minutes: 60, text: "1 hour"},
                    {minutes: 90, text: "1.5 hours"},
                    {minutes: 120, text: "2 hours"},
                    {minutes: 180, text: "3 hours"},
                    {minutes: 240, text: "4 hours"},
                    {minutes: 480, text: "all day"}
                ]
            }
        },

        methods: {
            increaseTimeSpan() {
                this.selectedTimeSpan = Math.min(this.selectedTimeSpan + 1, this.timeSpanList.length - 1);
            },

            decreaseTimeSpan() {
                this.selectedTimeSpan = Math.max(this.selectedTimeSpan - 1, 0);
            }
        }
    }
</script>
