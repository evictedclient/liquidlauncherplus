<script>
    import { createEventDispatcher } from "svelte";
    import SettingsContainer from "../settings/SettingsContainer.svelte";
    import Description from "../settings/Description.svelte";
    import ButtonSetting from "../settings/ButtonSetting.svelte";

    export let launchVersionWarningCountdown;

    const dispatch = createEventDispatcher();
</script>

<SettingsContainer
        title="You are about to launch a Laggy Memory Monster!1!!11!!!"
        on:hideSettings={() => dispatch('hide')}
>
    <Description
            description="zigger zigger zigger zigger zigger zigger zigger zigger zigger zigger"
    />
    <ButtonSetting
            text="Switch to legacy now"
            on:click={() => dispatch('switchToNextgen')}
            color="#8a0000"
    />
    <ButtonSetting
            disabled={launchVersionWarningCountdown > 0}
            text="Launch anyway{launchVersionWarningCountdown > 0 ? ` (${launchVersionWarningCountdown})` : ''}"
            on:click={() => dispatch('runClientAnyway')}
            color="#B83529"
    />
</SettingsContainer>