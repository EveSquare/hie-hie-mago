<template>
    <select :value="selector" @change="$emit('change', index, $event.target.value)">
        <option value="">🕵🏻‍♂️</option>
        <optgroup v-for="optgroup in optgroups" :label="optgroup.label">
            <option v-for="data in optgroup.data" :value="data">{{ data }}</option>
        </optgroup>
    </select>
    <button @click="$emit('removeSelector', index)">☠︎</button>
</template>

<script>
export default {
    props: {
        index: {
            type: Number,
            required: true,
        },
        selector: {
            type: String,
            required: true,
        },
    },
    data () {
        return {
            optgroups: [
                {
                    label: "家族",
                    data: [
                        "兄",
                        "弟",
                        "姉",
                        "妹",
                        "母",
                        "父",
                        "祖父母",
                        "子供",
                        "祖先",
                        "孫",
                    ],
                },
                {
                    label: "親戚",
                    data: [
                        "親戚",
                        "叔父",
                        "叔母",
                        "いとこ",
                        "甥",
                        "姪",
                    ],
                },
                {
                    label: "友人・仲間",
                    data: [
                        "友人",
                        "知人",
                        "仲間",
                        "クラスメート",
                        "チームメイト",
                        "同僚",
                        "先輩",
                        "後輩",
                    ],
                },
                {
                    label: "恋愛関係",
                    data: [
                        "配偶者",
                        "パートナー",
                        "片思いの相手",
                        "婚約者",
                        "元夫",
                        "元妻",
                    ], 
                },
                {
                    label: "教育関係",
                    data: [
                        "先生",
                        "生徒",
                        "メンター",
                        "担任教師",
                        "見習い",
                    ],
                },
                {
                    label: "その他の関係",
                    data: [
                        "上司",
                        "部下",
                        "従業員",
                        "保護者",
                        "知的パートナー",
                        "面会人",
                        "スポンサー",
                        "共同研究者",
                        "義兄弟",
                        "義姉妹",
                        "隠し子",
                        "心の支え",
                        "戦友",
                        "お世話になった人",
                        "見守り人",
                        "仲直り相手",
                        "スポーツライバル",
                        "目標とする人",
                        "ライバル",
                    ],
                },
            ]
        }
    },
}

</script>