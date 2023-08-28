<script lang="ts">
	export let tooltip: string = "";
	export let hoverColor: string = "";
	export let hoverTextColor: string = ""
</script>

<div class="btn" hover-tooltip={tooltip}
     style={`--btn-hover-color: ${hoverColor}; --btn-hover-text-color: ${hoverTextColor}`}>
	<button>
		<slot name="icon"/>
	</button>
</div>

<style lang="postcss">
    [hover-tooltip] {
        @apply relative cursor-pointer;

        &:after {
            content: attr(hover-tooltip);
            @apply text-center absolute whitespace-nowrap font-semibold left-[calc(100%+10px)] px-[14px] py-[4px] rounded-[6px] opacity-0 invisible transition-all bg-[#222127];
        }

        &:hover {
            &:after {
                @apply opacity-100 visible transition-all;
            }
        }
    }

    .btn {
        @apply relative w-full flex justify-center items-center;

        &:before {
            content: '';
            @apply absolute w-[4px] bg-white h-[22px] left-0 top-1/2 -translate-y-1/2 transition-all scale-0;
            border-radius: 0 4px 4px 0;
        }

        &:hover {
            &:before {
                @apply scale-100;
            }
        }

        &.active {
            &:before {
                content: '';
                @apply absolute w-[4px] bg-white h-full left-0 top-1/2 -translate-y-1/2 transition-all;
                border-radius: 0 4px 4px 0;
            }
        }
    }

    .btn:hover button {
        @apply text-white rounded-[14px];
        background: var(--btn-hover-color);
        animation: borders 0.3s linear;
        transition: background .4s;
    }

    button {
        @apply w-[48px] relative h-[48px] overflow-hidden rounded-full bg-[#313338] flex items-center justify-center;
        animation: defaultBorder 0.3s linear;
        transition: background .4s;
    }

    @keyframes defaultBorder {
        0% {
            @apply rounded-[14px];
        }
        50% {
            @apply rounded-[30px];
        }
        100% {
            @apply rounded-full ;
        }
    }

    @keyframes borders {
        0% {
            @apply rounded-full;
        }
        50% {
            @apply rounded-[30px];
        }
        100% {
            @apply rounded-[14px];
        }
    }
</style>