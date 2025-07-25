<script>
    import * as Highcharts from "highcharts";
    import "highcharts/modules/exporting";
    import { Chart } from "@highcharts/svelte";
    import Scroller from "../lib/Scroller.svelte";
    import ArticleText from "../lib/ArticleText.svelte";

    let options = {
        chart: {
            type: "pie",
        },
        title: {
            text: "Cities with the Most Redlining",
        },
        plotOptions: {
            pie: {
                allowPointSelect: true,
                dataLabels: [
                    {
                        enabled: true,
                        distance: 20,
                    },
                    {
                        enabled: true,
                        distance: -40,
                        format: "{point.percentage:.1f}%",
                        style: {
                            fontSize: "1.2em",
                            textOutline: "none",
                        },
                        filter: {
                            operator: ">",
                            property: "percentage",
                            value: 10,
                        },
                    },
                ],
            },
        },
        series: [
            {
                name: "Group",
                data: [
                    {
                        name: "Dallas",
                        y: 151,
                    },
                    {
                        name: "Group 2",
                        sliced: true,
                        selected: true,
                        y: 180,
                    },
                    {
                        name: "Group 3",
                        y: 32,
                    },
                    {
                        name: "Group 4",
                        y: 103,
                    },
                    {
                        name: "Group 5",
                        y: 77,
                    },
                ],
            },
        ],
    };
</script>

<div>
    <Scroller layout="right">
        {#snippet sticky()}
            <div class="chart">
                <Chart {options} highcharts={Highcharts} />
            </div>
            <p>
                Here's an example chart using
                <a href="https://www.highcharts.com/">Highcharts</a>!
            </p>
            <p>
                📈 <strong>Highcharts</strong> is a super-flexible library for
                creating all kinds of charts. See demos of different chart types
                <a href="https://www.highcharts.com/demo">here</a>.
            </p>
            <p>
                Since we're using Highcharts through Svelte, the syntax is a
                little different from what you might see in the demos. But all
                of Highcharts' functionality is available through the Highcharts
                for Svelte package.
            </p>
            <p>
                The configuration is done through the
                <code>options</code> json object passed to the chart, which you'll
                see in the source code for this template.
            </p>
            <p>
                Use the
                <a href="https://api.highcharts.com/highcharts/"
                    >API reference</a
                >
                to understand what each element in the <code>options</code> object
                does.
            </p>
        {/snippet}

        {#snippet scrolly()}
            <ArticleText>
                Redlining goes beyond just preventing African Americans from getting housing. It can also prevent getting access to good schools and having good education.
            </ArticleText>

            <ArticleText>
                According to this graph, around 20% of African Americans struggle with housing.
            </ArticleText>

            <ArticleText>
                The effects of this lack of high quality education lead to more issues in career growth.
            </ArticleText>

            <ArticleText>
                Thus, we see an overall lack of wealth. 
            </ArticleText>
        {/snippet}
    </Scroller>
</div>

<style>
    .chart {
        width: 90%;
        margin: 10px auto;
        padding-top: 100px;
    }
</style>
