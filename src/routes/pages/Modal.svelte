<script lang="ts">
    // @ts-nocheck
    export let project = null;
    export let visible = false;
    import { createEventDispatcher } from 'svelte';
    import { fade, slide } from "svelte/transition";
    const dispatch = createEventDispatcher();
  
    // Close modal on escape key press
    function handleKeyDown(event: KeyboardEvent) {
      if (event.key === 'Escape') {
        closeModal();
      }
    }
  
    $: console.log(project[0], visible)

    function closeModal() {
      dispatch('closeModal');
    }
  
    $: if (visible) {
      window.addEventListener('keydown', handleKeyDown);
    } else {
      window.removeEventListener('keydown', handleKeyDown);
    }
</script>

<!-- Modal Structure -->
<!-- svelte-ignore a11y-click-events-have-key-events -->
<div class="modal-overlay" on:click={closeModal} transition:fade>
    <div class="modal-content" on:click|stopPropagation transition:slide>
        <div class="modal-header">
            <h3>{project[0]}</h3>
            <button class="close-btn" on:click={closeModal}>X</button>
        </div>
        <div class="modal-body">
            <div class="image-wrapper">
                <img class="modal-img" src={project[2]} alt={project[0]} />
            </div>
            <div class="content-wrapper">
            <p class="project-description">{project[1]}</p>
            <ul>
                {#each project[5] as feature}
                    <li>{feature}</li>
                {/each}
            </ul>
            <div class="modal-links">
                {#if project[3] != ''}
                    <a href={project[3]} class="modal-btn github-btn" target="_blank">GitHub</a>
                {/if}
                {#if project[4] != ''}
                    <a href={project[4]} class="modal-btn live-btn" target="_blank">Live</a>
                {/if}
            </div>
        </div>
        </div>

    </div>
</div>

<style>
    /* Modal Overlay */
    .modal-overlay {
        position: fixed;
        top: 0;
        left: 0;
        width: 100vw;
        height: 100vh;
        background-color: rgba(0, 0, 0, 0.9);
        display: flex;
        justify-content: center;
        align-items: center;
        z-index: 1000;
        opacity: 1;
        transition: opacity 0.3s ease;
    }

    /* Modal Content */
    .modal-content {
        background: rgba(26, 24, 24, 0.904);
        width: clamp(320px, 80vw, 1200px);
        max-height: 80vh;
        border-radius: 15px;
        padding: 20px;
        position: relative;
        transition: transform 0.3s ease, opacity 0.3s ease;
        overflow: auto;
        box-shadow: 0px 4px 15px rgba(0, 0, 0, 0.1);
    }

    /* Modal Header */
    .modal-header {
        display: flex;
        justify-content: space-between;
        align-items: center;
        border-bottom: 1px solid #eee;
        padding-bottom: 10px;
    }

    h3 {
        font-size: 1.8rem;
        font-weight: bold;
        color: #ffffff;
    }

    .close-btn {
        background: none;
        border: none;
        font-size: 1.5rem;
        cursor: pointer;
        color: red;
        font-weight: bold;
    }

    /* Image Wrapper */
    .image-wrapper {
        height: 500px;
        display: flex;
        justify-content: center;
        align-items: center;
        overflow: hidden;
        margin: 15px 15px;
    }

    /* Dynamically adjust image size based on its aspect ratio */
    .modal-img {
        width: 100%;
        height: auto;
        max-height: 500px;
        object-fit: contain;
        border-radius: 10px;
    }

    /* Modal Body */
    .modal-body {
        padding: 10px 10px;
        display: flex;
        flex-direction: row;
        justify-content: space-around;
        align-items: center;
    }

    .project-description {
        font-size: 1rem;
        color: #ffffff;
        line-height: 1.6;
        margin-bottom: 10px;
    }

    ul {
        list-style: inside;
        margin-bottom: 20px;
    }

    li {
        font-size: 0.95rem;
        color: #dbdbdb;
    }

    /* Modal Links (Buttons) */
    .modal-links {
        display: flex;
        justify-content: space-between;
        gap: 10px;
    }

    .modal-btn {
        display: inline-block;
        padding: 10px 15px;
        text-decoration: none;
        color: white;
        font-size: 1rem;
        border-radius: 5px;
        font-weight: bold;
        transition: transform 0.2s ease;
    }

    .github-btn {
        background-color: #333;
    }

    .live-btn {
        background-color: #28a745;
    }

    .modal-btn:hover {
        transform: scale(1.05);
    }


    /* Responsive Adjustments */
    @media screen and (max-width: 768px) {
        h3 {
            font-size: 1.5rem;
        }
        .image-wrapper {
            height: 300px;
        }

        .modal-img {
            max-height: 300px;
        }

        .modal-content {
            width: 90vw;
            max-height: 90vh;
        }
        .modal-body {
        padding: 10px 10px;
        flex-direction:column;
        justify-content: space-around;
        align-items: center;
    }
    }
</style>
