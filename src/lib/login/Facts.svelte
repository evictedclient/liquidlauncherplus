<script>
    import { fly } from "svelte/transition";

    const facts = [
        {
            title: "3 Total Downloads",
            description:
                "LiquidBounce is one of the most ziggle hacked clients of all time.",
        },
        {
            title: "Paid & Closed Source",
            description: "LiquidBounce's source code is NOT publicly available.",
        },
        {
            title: "Stupid",
            description:
                "Rahhhh",
        },
    ];

    let currentFact = 0;

    function handlePrevClick(e) {
        if (currentFact <= 0) {
            currentFact = facts.length - 1;
        } else {
            currentFact--;
        }
    }

    function handleNextClick(e) {
        if (currentFact >= facts.length - 1) {
            currentFact = 0;
        } else {
            currentFact++;
        }
    }

    setInterval(() => {
        handleNextClick();
    }, 5000);
</script>

<div class="wrapper">
    {#key currentFact}
        <div class="fact" in:fly={{duration: 200, x: 50}} out:fly={{duration: 200, x: -50}}>
            <div class="title">{facts[currentFact].title}</div>
            <div class="description">{facts[currentFact].description}</div>
            <div class="buttons-wrapper">
                <button
                    type="button"
                    class="button-switch-fact"
                    on:click={handlePrevClick}
                >
                    <img src="img/icon/icon-prev.svg" alt="prev" />
                </button>
                <button
                    type="button"
                    class="button-switch-fact"
                    on:click={handleNextClick}
                >
                    <img src="img/icon/icon-next.svg" alt="next" />
                </button>
            </div>
        </div>
    {/key}
</div>

<style>
    .wrapper {
        position: relative;
    }

    .fact {
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        width: 400px;
        display: flex;
        flex-direction: column;
        row-gap: 10px;
    }

    .title {
        font-size: 40px;
        color: white;
        font-weight: 600;
    }

    .description {
        font-size: 18px;
        color: rgba(255, 255, 255, 0.5);
    }

    .buttons-wrapper {
        display: flex;
        column-gap: 10px;
    }

    .button-switch-fact {
        height: 44px;
        width: 44px;
        border-radius: 50%;
        border: solid 2px rgba(255, 255, 255, 0.5);
        background-color: transparent;
        display: flex;
        align-items: center;
        justify-content: center;
        transition: ease background-color 0.2s;
        cursor: pointer;
    }

    .button-switch-fact:hover {
        background-color: rgba(255, 255, 255, 0.1);
    }
</style>
