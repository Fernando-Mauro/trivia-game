<script>
    import {
        maxNumberOfQuestions,
        numberOfQuestions,
        hasQuizBegun,
        quizTitle,
    } from "../data/store";
    import { fly } from "svelte/transition";

    const onSubmit = () => {
        hasQuizBegun.set(true);
    };
</script>

<style>
    h1 {
        font-size: 1.8em;
        margin-bottom: 1em 0 2em 0;
        color: black;
    }
    label {
        margin: 2em 0;
        color: black;
        background: transparent;
    }
    input {
        background: transparent;
        border: 0;
        border-bottom: 2px solid black;
        color: black;
        text-align: center;
        display: block;
        margin: 0 auto;
    }
</style>

<div
    in:fly={{ x: 200, duration: 500, delay: 500 }}
    out:fly={{ x: -200, duration: 500 }}>
    <h1>{$quizTitle}!</h1>
    <form on:submit|preventDefault={onSubmit}>
        <label>
            ¿Cuántas preguntas quieres responder?
            <input
                type="number"
                bind:value={$numberOfQuestions}
                max={$maxNumberOfQuestions}
                min="1"
                required />
        </label>
        <button type="submit">Comenzar!</button>
        <p style="color: black">Intregantes:</p>
        <ul style="color: black">
            <li>Hernández Peralta Anaí</li>
            <li>López Mauro Fernando Francisco</li>
            <li>Castellanos Perez Naomi Michell</li>
            <li>Manuel Antonio Viviana</li>
            <li>Moralez Gonzales Leslie</li>
        </ul>
    </form>
</div>
