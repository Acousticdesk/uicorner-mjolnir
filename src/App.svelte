<script>
	import HolderName from './holderName.svelte'
	import Greetings from './Greetings.svelte'
	import Culmination from './Culmination.svelte'
	import Congratulations from './Congratulations.svelte'
	import NiceTry from './NiceTry.svelte'
	import { isFalse, isNull } from './utils'

	let name
	let isDeserve = null

	const authorize = () => {
        isDeserve = name === 'Thor' || name === 'Steve Rogers'
    }

    // Additional logic for letconst gurus 😋

	$: isInputDisabled = isDeserve
	$: isCulminationAvailable = name && isNull(isDeserve)

	const tryAgain = () => {
		isDeserve = null
		name = ''
	}
</script>

<Greetings />
<HolderName disabled={isInputDisabled} bind:value={name} />

{#if isCulminationAvailable}
	<Culmination name={name} authorize={authorize} />
{/if}

{#if isDeserve}
	<Congratulations name={name} />
{/if}

{#if isFalse(isDeserve)}
	<NiceTry tryAgain={tryAgain} />
{/if}
