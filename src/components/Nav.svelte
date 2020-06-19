<script>
	import { Button } from 'svelma';


	export function isSegmentActive(_segment, thisSegment) {
		if((!_segment && !thisSegment) || _segment === thisSegment) {
			return 'page';
		}
	}

	export let segment;
</script>

<style>
ul {
	display: flex;
	flex-direction: row;
	align-items: center;
}

a[aria-current="page"] {
	text-decoration: underline;
}
</style>

<nav>
	<ul>
		<li><a aria-current="{isSegmentActive(segment)}" href=".">Home</a></li>
		<li><a aria-current="{isSegmentActive(segment, 'scores')}" href="scores">High Scores</a></li>
		<li class="spacer"></li>
		<li><Button as="a" href="game">Play the Game!</Button></li>
	</ul>
</nav>
