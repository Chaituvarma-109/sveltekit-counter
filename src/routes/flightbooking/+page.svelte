<script>
    let travel = $state(false);
    let start = $state('');
    let end = $state('');

    let startDate = $derived(convertToDate(start));
    let endDate = $derived(convertToDate(end));

    function show() {
        let type = travel ? 'two-way' : 'one-way';

        let msg = `You have booked a ${type} flight on ${startDate.toDateString()}`;
        if (type === 'two-way') {
            msg += ` and return on ${endDate.toDateString()}`;
        }

        alert(msg);
    }

    function convertToDate(date) {
        const dateSplt = date.split('-');

        return new Date(dateSplt[0], dateSplt[1]-1, dateSplt[2]);
    }
</script>
<br/>

<select bind:value={travel}>
    <option value={false}>One-way</option>
    <option value={true}>Two-way</option>
</select>

<input type="date" bind:value={start}/>
<input type="date" bind:value={end} disabled="{!travel}"/>

<button type="submit" onclick={show}>Book</button>
