<script>
  // @ts-nocheck

  // image imports
  import AtlHome from "../lib/images/black-home-atl.png";
  import AtlNorthEdu from "../lib/images/white-edu-atl.png";
  import AtlEdu from "../lib/images/all-edu-atl.png";

  // component imports
  import Scroller from "../lib/Scroller.svelte";
  import ArticleText from "../lib/ArticleText.svelte";
  import Heading from "../lib/Heading.svelte";
  import Spacer from "../lib/Spacer.svelte";

  // chart imports
  import * as Highcharts from "highcharts";
  import "highcharts/modules/exporting";
  import { Chart } from "@highcharts/svelte";

  // academic performance comparison chart configuration
  const chartOptions = {
    chart: {
      type: "bar",
      backgroundColor: "transparent",
      style: { fontFamily: "Space Grotesk" },
      marginLeft: 175, // Otherwise "reading proficiency" gets cut off
    },
    title: {
      text: "Academic Performance Comparison",
      align: "left",
      style: {
        color: "var(--asparagus)",
        fontFamily: "DM Serif Text",
        fontSize: "1.5rem",
      },
    },
    xAxis: {
      categories: ["Math Proficiency", "Reading Proficiency"],
      labels: {
        overflow: "justify",
        reserveSpace: true,
        style: {
          color: "var(--pomp)",
          fontSize: "1rem",
        },
      },
    },
    yAxis: {
      min: 0, max: 100,
      title: {
        text: "Percent Proficient",
        style: {
          color: "var(--wenge)",
          fontSize: "1rem",
        },
      },
      labels: {
        format: "{value}%",
        style: {
          color: "var(--wenge)",
        },
      },
    },
    tooltip: {
      valueSuffix: "%",
      backgroundColor: "#f5f5f5",
      style: {
        color: "var(--wenge)",
      },
    },
    legend: {
      itemStyle: {
        color: "var(--wenge)",
        fontWeight: "bold",
      },
    },
    series: [
      {
        type: "bar",
        name: "Therrell High",
        color: "var(--rose)",
        data: [7, 18],
      },
      {
        type: "bar",
        name: "Walton High",
        color: "var(--asparagus)",
        data: [85, 88],
      },
    ],
    credits: {
      enabled: false,
    },
    caption: {
      text: "Public data from GreatSchools.org and Niche.com. <sup><a href='#source-1' id='ref-1'>1</a></sup><br />Therrell and Walton High are public high schools in the Atlanta metro area, although Therrell High is located in a poorer district in southern Atlanta with a higher Black population.",
    },
  };
</script>

<Spacer />

<Heading
  scene="// Track 2"
  title="Learning in the Margins"
  subtitle="&ldquo;[B]arriers include enrollment in underachieving schools, limited community resources, poverty, and the lack of prosocial and economic opportunities.&rdquo;"
  source="- St. Mary, Calhoun, Tejada, & Jenson (2018)"
/>

<Spacer />

<Scroller layout="right">
  {#snippet sticky()}
    <figure>
      <Chart {Highcharts} options={chartOptions} />
    </figure>
  {/snippet}

  {#snippet scrolly()}
    <div class="scene-text">
      <ArticleText>
        Ari is bright. She scores high on every test she takes - the few her
        overworked teachers still have time to give.
      </ArticleText>
      <ArticleText>
        But at her school, fewer than <strong>1 in 5</strong> are meeting
        proficiency in reading. Only <strong>7%</strong> are proficient in math.
      </ArticleText>
      <ArticleText>
        There's <strong>one</strong> counselor for over <strong>250</strong>
        students<sup><a href="#source-2" id="ref-2">2</a></sup>
        - often just one per grade.
      </ArticleText>
      <ArticleText>
        The school has a band, but no program for digital music production - the
        kind Ari dreams of. The nearest class like that? A 40-minute bus ride
        and a transfer away. There’s no one to help her craft a college plan -
        no one to even ask if she’s considered one.
      </ArticleText>
    </div>
  {/snippet}
</Scroller>

<Spacer />

<Scroller layout="right">
  {#snippet sticky()}
    <figure>
      <img
        src={AtlEdu}
        alt="Bachelor degree attainment falls under 15% in areas of Southern Atlanta."
      />
      <figcaption>
        In some tracts of Southern Atlanta with a high concentration of Black
        residents, only 14.2% hold a bachelor’s degree.<sup
          ><a href="#source-3" id="ref-3">3</a></sup
        >
      </figcaption>
    </figure>
    <figure>
      <img
        src={AtlNorthEdu}
        alt="Bachelor degree attainment for white people surpasses 80.6% in wealthy areas of Northern Atlanta."
      />
      <figcaption>
        In Northern Atlanta, over 80% of white adults hold a bachelor’s degree.<sup
          ><a href="#source-3" id="ref-3">3</a></sup
        >
      </figcaption>
    </figure>
  {/snippet}

  {#snippet scrolly()}
    <div class="scene-text">
      <ArticleText>
        In Ari's district in Atlanta, which is <strong>98.9% black</strong><sup
          ><a href="#source-3" id="ref-3">3</a></sup
        >, less than <strong>1 in 6</strong>
        have a college degree. Compare that to over <strong>85%</strong> of White
        adults in wealthier areas of the same city.
      </ArticleText>
      <ArticleText>
        It’s not about ability - it’s about access. It’s about schools being
        funded by property taxes. It’s about <em>zip codes</em> acting like
        <em>invisible gates.</em>
      </ArticleText>
      <div class="thought">
        <ArticleText>
          <i
            >I watch YouTube videos until my eyes burn. Reddit threads teach me
            more about mixing than any class ever could. But I shouldn't have to
            learn everything myself.</i
          >
        </ArticleText>
      </div>
    </div>
  {/snippet}
</Scroller>

<style>
  figure {
    margin-top: 2rem;
    text-align: center;
  }
  figcaption {
    font-family: "Space Grotesk", sans-serif;
    font-size: 0.9rem;
    color: var(--wenge);
    margin-top: 0.75rem;
    max-width: 500px;
    margin-left: auto;
    margin-right: auto;
  }
  img {
    width: 48vh;
  }
</style>
