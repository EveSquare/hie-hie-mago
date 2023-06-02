<template>
    <select :value="selector" @change="$emit('change', index, $event.target.value)">
        <option value="">🕵🏻‍♂️</option>
        <optgroup label="家族">
            <option>兄弟姉妹</option>
            <option>母</option>
            <option>父</option>
            <option>祖父母</option>
            <option>子供</option>
            <option>祖先</option>
            <option>孫</option>
        </optgroup>
        <optgroup label="親戚">
            <option>親戚</option>
            <option>叔父・叔母</option>
            <option>いとこ</option>
            <option>甥・姪</option>
        </optgroup>
        <optgroup label="友人・仲間">
            <option>友人</option>
            <option>知人</option>
            <option>仲間</option>
            <option>クラスメート</option>
            <option>チームメイト</option>
            <option>同僚</option>
            <option>先輩</option>
            <option>後輩</option>
        </optgroup>
        <optgroup label="恋愛関係">
            <option>配偶者</option>
            <option>パートナー</option>
            <option>片思いの相手</option>
            <option>元夫・元妻</option>
            <option>婚約者</option>
        </optgroup>
        <optgroup label="教育関係">
            <option>先生</option>
            <option>生徒</option>
            <option>メンター</option>
            <option>メンティー</option>
            <option>担任教師</option>
            <option>見習い</option>
        </optgroup>
        <optgroup label="その他の関係">
            <option>上司</option>
            <option>部下</option>
            <option>保護者</option>
            <option>知的パートナー</option>
            <option>面会人</option>
            <option>スポンサー</option>
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
}

</script>