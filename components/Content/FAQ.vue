<template>
  <section id="FAQ">
    <div class="faq__title">
      <h1 class="faq__title-text">Frequently asked questions</h1>
    </div>

    <div class="accordion">
      <details class="accordion__item" name="faq">
        <summary class="accordion__summary">
          <span class="accordion__summary-title" role="term" aria-details="faq-1"> What is A2A.Global? </span>
        </summary>
      </details>

      <div class="accordion__content" id="faq-1" role="definition">
        <div class="accordion__content-body">
          <p>
            A2A.Global is a payments processing company that revolutionises how payments are made. We believe that card
            payments are the artifacts of the past, and direct account-to-account bank payments via simple buy fast
            button are modernising the payment industry and client habits
          </p>
        </div>
      </div>
    </div>

    <div class="accordion">
      <details class="accordion__item" name="faq">
        <summary class="accordion__summary">
          <span class="accordion__summary-title" role="term" aria-details="faq-1"> How does it work? </span>
        </summary>
      </details>

      <div class="accordion__content" id="faq-1" role="definition">
        <div class="accordion__content-body">
          <p>
            We install “buy fast” button to businesses for any type of client interaction: <br />
            ⦁ Online (desktop, mobile, app) <br />
            ⦁ Offline <br />
            ⦁ Messenger, email <br />
            Payer will only need her mobile smartphone in hand. Clicks the buy fast button, chooses her bank from
            dropdown list, confirms the transaction and bingo – the payment is made No credit card details required
          </p>
        </div>
      </div>
    </div>

    <div class="accordion">
      <details class="accordion__item" name="faq">
        <summary class="accordion__summary">
          <span class="accordion__summary-title" role="term" aria-details="faq-1">
            Why should I choose A2A.Global?
          </span>
        </summary>
      </details>

      <div class="accordion__content" id="faq-1" role="definition">
        <div class="accordion__content-body">
          <p>
            Easy choice! A2A.Global is low cost and easy for integration. It will help you to increase your client base
            as well as raise your conversion rate at checkout, and provide instant cash inflows into your business! More
            details below: <br />
            ⦁ Cost: low and transparent cost structure (0,5% + 1 cent) + 3 months free trial [here it is a clickable
            link ] <br />
            ⦁ Ease of integration: payment button is easily integrated into website, mobile site, app or offline point
            <br />
            ⦁ Client base increase: A2A payment is a key customer trend that will attract various clients from the
            world, A2A.global attracts dozens of new banks-partners every quarter whose clients could become your new
            client base <br />
            ⦁ Conversion at checkout increase: “buy fast” payment button is instant and frictionless payment method (no
            credit card required – only the mobile phone), therefore, will dramatically increase the conversion rates
            <br />⦁ Instant cash inflow: shorter settlement times, more money for your business at any given point of
            time
          </p>
        </div>
      </div>
    </div>

    <div class="accordion">
      <details class="accordion__item" name="faq">
        <summary class="accordion__summary">
          <span class="accordion__summary-title" role="term" aria-details="faq-1">
            I make payments online and offline with credit card, apple/google pay, it is convenient for me, why would I
            choose A2A.Global?
          </span>
        </summary>
      </details>

      <div class="accordion__content" id="faq-1" role="definition">
        <div class="accordion__content-body">
          <p>
            Great question! Below are the key benefits for you: <br />
            ⦁ Earn: Cashback on any transaction <br />
            ⦁ Cost: low FX cost <br />
            ⦁ Speed: Instant <br />
            ⦁ Security: no bank or credit card details exposed <br />
            ⦁ Ease of use: frictionless experience (only mobile phone required)
          </p>
        </div>
      </div>
    </div>

    <div class="accordion">
      <details class="accordion__item" name="faq">
        <summary class="accordion__summary">
          <span class="accordion__summary-title" role="term" aria-details="faq-1">
            I have more questions, how and whom could I ask them?
          </span>
        </summary>
      </details>

      <div class="accordion__content" id="faq-1" role="definition">
        <div class="accordion__content-body">
          <p>
            Thank you for your interest! Our sales team and founders are available to you 24/7, please submit your
            question and choose available time slots in the calendry link below
          </p>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.faq__title {
  font-size: calc(28px + (20 + 20 * 0.7) * (100vw - 375px) / 1920);
  letter-spacing: -1px;
  font-weight: 600;
  text-align: center;
  margin-bottom: 40px;
}

.faq__title-text {
  font-size: calc(28px + (20 + 20 * 0.7) * (100vw - 375px) / 1920);
  text-align: center;
  margin-bottom: 16px;
  font-weight: 600;
  letter-spacing: -1px;
}

.accordion {
  padding: 20px;
  border-radius: 24px;
  background-color: #f2f2f2;
  margin-bottom: 16px;
}

.accordion__content {
  display: grid;
  grid-template-rows: 0fr;
  align-self: end;
  transition: all 0.3s ease-out;
}

.accordion__content-body {
  overflow: hidden;
}

.accordion__content-body > p {
  margin-top: 20px;
  color: #656565;
  letter-spacing: -0.5px;
  font-weight: 300;
  line-height: 140%;
}

.accordion__item[open] + .accordion__content {
  grid-template-rows: 1fr;
  margin-bottom: 20px;
}

.accordion__summary-title {
  font-weight: 400;
  letter-spacing: -0.5px;
  font-size: calc(18px + (6 + 6 * 0.7) * (100vw - 375px) / 1920);
}

details {
  position: relative;
  -webkit-appearance: none;
  appearance: none;
}

details[open] summary {
  list-style: none;
}

details summary::-webkit-details-marker {
  display: none;
}

summary {
  list-style: none;
  cursor: pointer;
}

details > summary::before {
  content: "›";
  font-size: calc(18px + (6 + 6 * 0.7) * (100vw - 375px) / 1920);
  transform: rotate(90deg);
  line-height: 100%;
  position: absolute;
  right: 0;
  top: 2px;
  transition: all 0.2s ease-in-out;
}

details[open] > summary::before {
  transform: rotate(270deg);
}
</style>
