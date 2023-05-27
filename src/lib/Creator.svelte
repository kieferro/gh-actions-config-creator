<script lang="ts">
    import WorkflowName from "./WorkflowName.svelte";
    import RunName from "./RunName.svelte";
    let workflowName: string = "";
    let runName: string = "";
</script>

<div id="container">
    <div id="input" class="field">
        <WorkflowName bind:workflowName={workflowName}></WorkflowName>
        <br>
        <RunName bind:runName={runName}></RunName>
    </div>
    <div id="output" class="field">
        <pre><code>name: {workflowName}</code>{#if runName.length}<code>

run-name: {runName}</code>{/if}

<code>[Jobs]</code></pre>
    </div>
</div>

<style>
    #container {
        display: flex;
        flex-direction: row;
        flex-wrap: nowrap;
        justify-content: space-evenly;
        align-items: flex-start;
        padding-top: 30px;
    }
    .field {
        background: rgba(140, 130, 130, 0.1);
		width: 47%;
        border-radius: 5px;
        min-height: 500px;
        padding: 10px;
    }
    #output pre {
        border: 1px solid red;
		font-size: 12px;
		line-height: 20px;
        margin: 0;
    }
</style>

