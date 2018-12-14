/**
Progress bar is not implemented, the best approach is the main data (object or array) be declared 
in top parent (App.vue, in this case)
 */
<template>
    <div>
        <h3>Quotes Added</h3>
        <div class="progress">
            <div class="progress-bar" 
                 role="progressbar" 
                 aria-valuenow="60" 
                 aria-valuemin="0" 
                 aria-valuemax="100"
                 :style="{width: (quoteCount / maxQuotes) * 100 + '%'}">
                {{ quoteCount }} / {{ maxQuotes }}
	        </div>
        </div>
    </div>	
</template>

<script>
    export default {
        props: ['quoteCount', 'maxQuotes']
    }
</script>
