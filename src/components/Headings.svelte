<script>
	export let headings = [];
	export let post = {};

	const isPost = Boolean(Object.keys(post).length);

	if (isPost) headings = post.getHeadings();
</script>

{#each headings as heading}
	<div class="mb-2 flex">
		<span
			class="mr-1 text-neutral-300"
			class:ml-4={heading.depth == 3}
			class:ml-8={heading.depth == 4}
			class:ml-12={heading.depth == 5}
			class:ml-16={heading.depth == 6}
		>
			#
		</span>
		<a
			class="font-normal"
			href={isPost ? `${post.url}#${heading.slug}` : `#${heading.slug}`}
		>
			{heading.text}
		</a>
	</div>
{/each}
