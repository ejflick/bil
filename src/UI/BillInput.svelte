<script>
    import { createEventDispatcher } from 'svelte';
    import { Container, Button, Form, FormGroup, FormText, Input, Label } from 'sveltestrap';

    let name = '';
    let start = '';
    let end = '';
    let amount = '';

    const dispatch = createEventDispatcher();

    function addBill() {
        dispatch('addBill', {
            name,
            period: { start: new Date(), end: new Date() },
            amount
        });

        name = '';
        start = '';
        end = '';
        amount = '';
    }
</script>

<Container>
    <Form>
        <FormGroup>
            <Label for="name">Name:</Label>
            <Input type="text" bind:value={name} />
        </FormGroup>
        <FormGroup>
            <Label for="name">Start:</Label>
            <Input type="date" bind:value={start} />
        </FormGroup>
        <FormGroup>
            <Label for="name">End:</Label>
            <Input type="date" placeholder="time placeholder" bind:value={end} />
        </FormGroup>
        <FormGroup>
            <Label for="name">Amount:</Label>
            <Input type="number" bind:value={amount} />
        </FormGroup>

        <Button type="button" primary on:click={addBill}>Add bill</Button>
    </Form>
</Container>