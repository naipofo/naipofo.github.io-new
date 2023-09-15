<div>
    <slot />
</div>

<style>
    div {
		border-image: url('/phone-frame.svg');
		border-style: solid;
		border-image-width: 27px 42px 27px 43px;
		border-image-outset: 27px 42px 27px 43px;
		border-image-slice: 37 51 37 53 fill;
		border-image-repeat: repeat;
		width: 300px;
		height: 120px;
		overflow: hidden;
		padding: 27px 50px 27px 43px;
		margin: 3rem;
		font-family: monospace;
		color: #242815;
		word-break: break-all;
		padding: 0.8rem;
		border-radius: 3px;
	}
</style>