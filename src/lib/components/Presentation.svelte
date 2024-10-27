<script lang="ts">
	import Slide from './Slide.svelte';
	import Code from './Code.svelte';
	import Markdown from './Markdown.svelte';
	import Notes from './Notes.svelte';
	import * as m from '$lib/paraglide/messages.js';
</script>

<Slide animate>
	<h3>{m.what_is_svelte()}</h3>
	<Notes>Give usefull info</Notes>
</Slide>
<Slide animate>
	<h3>{m.what_is_svelte()}</h3>
	<p>{m.svelte_is()}</p>
</Slide>

<Slide animate>
	<h3>{m.what_make_svelte_special()}</h3>
</Slide>

<Slide animate>
	<h3>{m.what_make_svelte_special()}</h3>
	<p>{m.svelte_is_special()}</p>
</Slide>

<Slide animate>
	<h3>{m.svelte_vs_react()}</h3>
</Slide>

<Slide animate>
	<h3>{m.svelte_vs_react()}</h3>
	<ul>
		<li>{m.svelte_vs_react_text_1()}</li>
	</ul>
</Slide>

<Slide animate>
	<h3>{m.svelte_vs_react()}</h3>
	<ul>
		<li>{m.svelte_vs_react_text_1()}</li>
		<li>{m.svelte_vs_react_text_2()}</li>
	</ul>
</Slide>

<Slide animate>
	<h3>{m.svelte_vs_react()}</h3>
	<ul>
		<li>{m.svelte_vs_react_text_1()}</li>
		<li>{m.svelte_vs_react_text_2()}</li>
		<li>{m.svelte_vs_react_text_3()}</li>
	</ul>
</Slide>

<Slide animate>
	<h3>React one-way binding</h3>
	<Code id="React-1" noescape lines="1-15">
		{`
			import React, { useState } from 'react';

			function Counter() {
				const [count, setCount] = useState(0);

				return (
					<div>
						<h1>One-Way Data Binding in React</h1>
						<p>Count: {count}</p>
						<button onClick={() => setCount(count + 1)}>Increment</button>
					</div>
				);
			}
			
			export default Counter;
		`}
	</Code>
</Slide>

<Slide animate>
	<h3>React one-way binding</h3>
	<Code id="React-1" noescape lines="4">
		{`
			import React, { useState } from 'react';

			function Counter() {
				const [count, setCount] = useState(0);
			
				return (
					<div>
						<h1>One-Way Data Binding in React</h1>
						<p>Count: {count}</p>
						<button onClick={() => setCount(count + 1)}>Increment</button>
					</div>
				);
			}
			
			export default Counter;
		`}
	</Code>
</Slide>

<Slide animate>
	<h3>Svelte 4 one-way binding</h3>
	<Code id="Svelte-1" noescape lines="1-7">
		{`
			<script>
				let count = 0;
			</script>

			<h1>One-Way Data Binding in Svelte</h1>
			<p>Count: {count}</p>
			<button on:click={() => count += 1}>Increment</button>`}
	</Code>
</Slide>

<Slide animate>
	<h3>Svelte 4 one-way binding</h3>
	<Code id="Svelte-1" noescape lines="2">
		{`
			<script>
				let count = 0;
			</script>

			<h1>One-Way Data Binding in Svelte</h1>
			<p>Count: {count}</p>
			<button on:click={() => count += 1}>Increment</button>`}
	</Code>
</Slide>

<Slide animate>
	<h3>Svelte 5 one-way binding</h3>
	<Code id="Svelte-2" noescape lines="2">
		{`
			<script>
				let count = $state(0);
			</script>

			<h1>One-Way Data Binding in Svelte</h1>
			<p>Count: {count}</p>
			<button on:click={() => count += 1}>Increment</button>`}
	</Code>
</Slide>

<Slide animate>
	<h3>React list rendering</h3>
	<Code id="React-2" noescape lines="1-15">
		{`
			import React from 'react';

			function List() {
				const items = ['Item 1', 'Item 2', 'Item 3'];

				return (
					<ul>
						{items.map((item, index) => (
							<li key={index}>{item}</li>
						))}
					</ul>
				);
			}
			
			export default List;
		`}
	</Code>
</Slide>

<Slide animate>
	<h3>React list add new Item</h3>
	<Code id="React-2" noescape lines="1-25">
		{`
			import React, { useState } from 'react';

			function List() {
				const [items, setItems] = useState(['Item 1', 'Item 2', 'Item 3']);
				const [newItem, setNewItem] = useState('');

				const addItem = () => {
					setItems([...items, newItem]);
					setNewItem('');
				};

				return (
					<div>
						<ul>
							{items.map((item, index) => (
								<li key={index}>{item}</li>
							))}
						</ul>
						<input type="text" value={newItem} onChange={(e) => setNewItem(e.target.value)} />
						<button onClick={addItem}>Add Item</button>
					</div>
				);
			}
			
			export default List;
		`}
	</Code>
</Slide>

<Slide animate>
	<h3>Svelte 5 list add new Item</h3>
	<Code id="Svelte-3" noescape lines="1-16">
		{`
			<script>
				let items = $state(['Item 1', 'Item 2', 'Item 3']);
				let newItem = $state('');

				function addItem() {
					items.push(newItem);
				}
			</script>

			<ul>
				{#each items as item, index}
					<li key={index}>{item}</li>
				{/each}
			</ul>
			<input type="text" bind:value={newItem} />
			<button onclick={addItem}>Add Item</button>`}
	</Code>
</Slide>

<Slide animate>
	<h3>React conditional rendering</h3>
	<Code id="React-3" noescape lines="1-15">
		{`
			import React, { useState } from 'react';

			function Conditional() {
				const [show, setShow] = useState(false);

				return (
					<div>
						<button onClick={() => setShow(!show)}>Toggle</button>
						{show && <p>Conditional Rendering in React</p>}
					</div>
				);
			}
			
			export default Conditional;
		`}
	</Code>
</Slide>

<Slide animate>
	<h3>Svelte 5 conditional rendering</h3>
	<Code id="Svelte-4" noescape lines="1-8">
		{`
			<script>
				let show = $state(false);
			</script>

			<button on:click={() => show = !show}>Toggle</button>
			{#if show}
				<p>Conditional Rendering in Svelte</p>
			{/if}`}
	</Code>
</Slide>

<Slide animate>
	<h3>React Promise handle</h3>
	<Code id="React-4" noescape lines="1-23">
		{`
			import React, { useState } from 'react';

			function Promise() {
				const [data, setData] = useState(null);
				const [loading, setLoading] = useState(false);

				const fetchData = async () => {
					setLoading(true);
					const response = await fetch('https://jsonplaceholder.typicode.com/posts/1');
					const json = await response.json();
					setData(json);
					setLoading(false);
				};

				return (
					<div>
						<button onClick={fetchData}>Fetch Data</button>
						{loading ? <p>Loading...</p> : <p>{data?.title}</p>}
					</div>
				);
			}
			
			export default Promise;
		`}
	</Code>
</Slide>

<Slide animate>
	<h3>Svelte 5 Promise handle</h3>
	<Code id="Svelte-5" noescape lines="1-16">
		{`
			<script lang="ts">
				let asyncData = $state<Promise<any> | null>(null)

				async function fetchData() {
					const response = await fetch('https://jsonplaceholder.typicode.com/posts/1');
					const json = await response.json();
					return json;
				}
			</script>
			
			<button onclick={() => asyncData = fetchData()}>Fetch Data</button>
			{#await asyncData}
				<p>Loading...</p>
			{:then data}
				<p>{data?.title}</p>
			{/await}`}
	</Code>
</Slide>

<Slide animate>
	<h3>Svelte 5 Reactivity outside the component</h3>
	<Code id="Svelte-6" noescape lines="1-26">
		{`
			// store.svelte.ts
			class Counter {
				count = $state(0);

				constructor(initialCount = 0) {
					this.count = initialCount;
				}

				increment() {
					this.count += 1;
				}

				decrement() {
					this.count -= 1;
				}

				reset() {
					this.count = 0;
				}

				setCount(value) {
					this.count = value;
				}
			}
			
			export const counter = new Counter();`}
	</Code>
</Slide>

<Slide animate>
	<h3>Svelte 5 using global counter in component</h3>
	<Code id="Svelte-6" noescape lines="1-24">
		{`
			<script>
				import { counter } from './store.svelte.ts';
			</script>

			<h1>Global Counter</h1>
			<p>Count: {store.count}</p>
			<button onclick={() => counter.increment()}>Increment</button>
			<button onclick={() => counter.decrement()}>Decrement</button>
			<button onclick={() => counter.reset()}>Reset</button>
			<input type="number" bind:value={counter.count} />`}
	</Code>
</Slide>
