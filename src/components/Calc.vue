<template>
    <v-container>
        <v-row class="text-center">
            <v-col cols="12">
                <h1>Bcalc</h1>
                <!-- Calc Body -->
                <v-sheet
                    elevation="18"
                    class="mx-auto pa-3"
                    height="480"
                    width="320"
                    color="#37474F"
                >
                    <!-- Display -->
                    <v-row class="text-center">
                        <v-sheet
                            elevation="1"
                            class="mx-auto my-4"
                            height="80"
                            width="280"
                            color="#455A64"
                        >
                            <v-row>
                                <v-col
                                    cols="12"
                                    class="pa-5"
                                    align="right"
                                    justify="center"
                                >
                                    <span
                                        data-cy="bc-display"
                                        class="text-h4 white--text"
                                        >{{ formattedDisplay }}</span
                                    >
                                </v-col>
                            </v-row>
                        </v-sheet>
                    </v-row>
                    <!-- First Button Row    -->
                    <v-row class="ma-2" align="center" justify="center">
                        <v-col cols="3" class="pa-0">
                            <v-btn
                                data-cy="bc-Clr"
                                fab
                                dark
                                color="blue"
                                @click="clear"
                            >
                                <span class="text-h5">C</span>
                            </v-btn>
                        </v-col>
                        <v-col cols="3" class="pa-0">
                            <v-btn
                                data-cy="bc-Sig"
                                fab
                                dark
                                color="blue"
                                @click="signal"
                            >
                                <v-icon dark>mdi-plus-minus-variant</v-icon>
                            </v-btn>
                        </v-col>
                        <v-col cols="3" class="pa-0">
                            <v-btn
                                data-cy="bc-Per"
                                fab
                                dark
                                color="blue"
                                @click="percent"
                            >
                                <v-icon dark>mdi-percent-outline</v-icon>
                            </v-btn>
                        </v-col>
                        <v-col cols="3" class="pa-0">
                            <v-btn
                                data-cy="bc-Div"
                                fab
                                dark
                                color="orange"
                                @click="operationClicked('/')"
                            >
                                <v-icon dark>mdi-division</v-icon>
                            </v-btn>
                        </v-col>
                    </v-row>
                    <!-- Second Button Row    -->
                    <v-row class="ma-2" align="center" justify="center">
                        <v-col cols="3" class="pa-0">
                            <v-btn
                                data-cy="bc-btn7"
                                fab
                                dark
                                color="#304FFE"
                                @click="append(7)"
                            >
                                <span class="text-h5">7</span>
                            </v-btn>
                        </v-col>
                        <v-col cols="3" class="pa-0">
                            <v-btn
                                data-cy="bc-btn8"
                                fab
                                dark
                                color="#304FFE"
                                @click="append(8)"
                            >
                                <span class="text-h5">8</span>
                            </v-btn>
                        </v-col>
                        <v-col cols="3" class="pa-0">
                            <v-btn
                                data-cy="bc-btn9"
                                fab
                                dark
                                color="#304FFE"
                                @click="append(9)"
                            >
                                <span class="text-h5">9</span>
                            </v-btn>
                        </v-col>
                        <v-col cols="3" class="pa-0">
                            <v-btn
                                data-cy="bc-Mul"
                                fab
                                dark
                                color="orange"
                                @click="operationClicked('*')"
                            >
                                <span class="text-h5">X</span>
                            </v-btn>
                        </v-col>
                    </v-row>
                    <!-- Third Button Row    -->
                    <v-row class="ma-2" align="center" justify="center">
                        <v-col cols="3" class="pa-0">
                            <v-btn
                                data-cy="bc-btn4"
                                fab
                                dark
                                color="#304FFE"
                                @click="append(4)"
                            >
                                <span class="text-h5">4</span>
                            </v-btn>
                        </v-col>
                        <v-col cols="3" class="pa-0">
                            <v-btn
                                data-cy="bc-btn5"
                                fab
                                dark
                                color="#304FFE"
                                @click="append(5)"
                            >
                                <span class="text-h5">5</span>
                            </v-btn>
                        </v-col>
                        <v-col cols="3" class="pa-0">
                            <v-btn
                                data-cy="bc-btn6"
                                fab
                                dark
                                color="#304FFE"
                                @click="append(6)"
                            >
                                <span class="text-h5">6</span>
                            </v-btn>
                        </v-col>
                        <v-col cols="3" class="pa-0">
                            <v-btn
                                data-cy="bc-Sub"
                                fab
                                dark
                                color="orange"
                                @click="operationClicked('-')"
                            >
                                <v-icon dark>mdi-minus</v-icon>
                            </v-btn>
                        </v-col>
                    </v-row>
                    <!-- Fouth Button Row    -->
                    <v-row class="ma-2" align="center" justify="center">
                        <v-col cols="3" class="pa-0">
                            <v-btn
                                data-cy="bc-btn1"
                                fab
                                dark
                                color="#304FFE"
                                @click="append(1)"
                            >
                                <span class="text-h5">1</span>
                            </v-btn>
                        </v-col>
                        <v-col cols="3" class="pa-0">
                            <v-btn
                                data-cy="bc-btn2"
                                fab
                                dark
                                color="#304FFE"
                                @click="append(2)"
                            >
                                <span class="text-h5">2</span>
                            </v-btn>
                        </v-col>
                        <v-col cols="3" class="pa-0">
                            <v-btn
                                data-cy="bc-btn3"
                                fab
                                dark
                                color="#304FFE"
                                @click="append(3)"
                            >
                                <span class="text-h5">3</span>
                            </v-btn>
                        </v-col>
                        <v-col cols="3" class="pa-0">
                            <v-btn
                                data-cy="bc-btnAdd"
                                fab
                                dark
                                color="orange"
                                @click="operationClicked('+')"
                            >
                                <v-icon dark>mdi-plus</v-icon>
                            </v-btn>
                        </v-col>
                    </v-row>
                    <!-- Fifth Button Row    -->
                    <v-row class="ma-2" align="center" justify="center">
                        <v-col cols="6" class="pa-0">
                            <v-btn
                                data-cy="bc-btn0"
                                width="126"
                                height="56"
                                rounded
                                large
                                dark
                                color="#304FFE"
                                @click="append(0)"
                            >
                                <span class="text-h5">0</span>
                            </v-btn>
                        </v-col>
                        <v-col cols="3" class="pa-0">
                            <v-btn
                                data-cy="bc-decimal"
                                fab
                                dark
                                color="#304FFE"
                                @click="insertDecimal()"
                            >
                                <span class="text-h5">{{ decimalChar }}</span>
                            </v-btn>
                        </v-col>
                        <v-col cols="3" class="pa-0">
                            <v-btn
                                data-cy="bc-equal"
                                fab
                                dark
                                color="orange"
                                @click="equal()"
                            >
                                <v-icon dark>mdi-equal</v-icon>
                            </v-btn>
                        </v-col>
                    </v-row>
                </v-sheet>
            </v-col>
        </v-row>
    </v-container>
</template>

<script>
const MAX_DIGITS = 12;

export default {
    name: "Calc",
    data: () => ({
        decimalChar: ".",
        formattedDisplay: "0",
        rawDisplay: "",
        nextNumber: false,
        operand1: "",
        operation: "",
        operand2: "",
    }),
    methods: {
        append(num) {
            if (this.nextNumber) {
                this.rawDisplay = "";
                this.nextNumber = false;
            }
            if (this.rawDisplay.length < MAX_DIGITS) {
                this.rawDisplay = `${this.rawDisplay}${num}`;
            }
        },
        clear() {
            this.rawDisplay = "";
            this.nextNumber = false;
            this.operation = "";
            this.operand1 = "";
            this.operand2 = "";
        },
        signal() {
            if (this.rawDisplay.charAt(0) === "-") {
                this.rawDisplay = `${this.rawDisplay.slice(1)}`;
            } else {
                this.rawDisplay = `-${this.rawDisplay}`;
            }
        },
        insertDecimal() {
            if (this.rawDisplay.indexOf(".") === -1) {
                if (this.rawDisplay === "") {
                    this.rawDisplay = "0";
                }
                this.rawDisplay = `${this.rawDisplay}.`;
            }
        },
        percent() {
            this.rawDisplay = `${this.rawDisplay / 100}`;
        },
        precision(num) {
            return num.indexOf(".") === -1
                ? -1
                : num.length - num.indexOf(".") - 1;
        },
        digits(num) {
            return num.length;
        },
        operationClicked(oper) {
            if (this.operand1 !== "") {
                this.operand2 = this.rawDisplay;
                this.evaluate();
            }
            this.nextNumber = true;
            this.operand1 = this.rawDisplay;
            this.operation = oper;
        },
        equal() {
            this.operand2 = this.rawDisplay;
            this.evaluate();
        },
        evaluate() {
            try {
                let value = String(
                    this.parse(
                        `${this.operand1} ${this.operation} ${this.operand2}`
                    )
                );
                if (isNaN(value)) throw "Error";
                this.rawDisplay = this.adjustPrecision(value);
            } catch {
                this.formattedDisplay = "Error";
            }
            this.nextOperand();
        },
        adjustPrecision(num) {
            let precision = this.precision(num);
            let digits = this.digits(num);
            let precisionAdjusted = num;
            let newPrecision = MAX_DIGITS - (digits - precision + 1);

            if (digits > MAX_DIGITS) {
                precisionAdjusted = this.round(num, newPrecision);
                if (precisionAdjusted.length > MAX_DIGITS) {
                    throw "Overflow";
                }
            }
            return precisionAdjusted;
        },
        round(num, places) {
            const x = Math.pow(10, places);
            return String(Math.round(num * x) / x);
        },
        parse(str) {
            return Function(`'use strict'; return (${str})`)();
        },
        nextOperand() {
            this.nextNumber = true;
            this.operand1 = "";
            this.operand2 = "";
            this.operation = "";
        },
        getFormattedNumber(num) {
            let minDigit = this.precision(num);
            let value = Number(num).toLocaleString(undefined, {
                maximumFractionDigits: MAX_DIGITS,
                minimumFractionDigits: minDigit < 0 ? 0 : minDigit,
            });
            return value;
        },
    },
    watch: {
        rawDisplay(val) {
            if (val.slice(-1) === ".") {
                this.formattedDisplay = `${this.getFormattedNumber(val)}${","}`;
            } else {
                this.formattedDisplay = this.getFormattedNumber(val);
            }
        },
    },
    mounted() {
        this.decimalChar = Number("1")
            .toLocaleString(undefined, {
                minimumFractionDigits: 8,
            })
            .charAt(1);
    },
};
</script>

