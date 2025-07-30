<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Income Inequality Game</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <style>
    body {
      font-family: 'Inter', sans-serif;
      background-color: #f9fafb;
      min-height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      padding: 20px;
      box-sizing: border-box;
    }
    .container {
      background: white;
      border-radius: 12px;
      max-width: 900px;
      width: 100%;
      padding: 30px;
      box-shadow: 0 8px 20px rgba(0,0,0,0.1);
      display: flex;
      flex-direction: column;
      gap: 20px;
    }
    .card {
      border: 1px solid #d1d5db;
      border-radius: 10px;
      padding: 18px;
      cursor: pointer;
      transition: all 0.2s ease-in-out;
      user-select: none;
    }
    .card:hover {
      border-color: #2563eb;
      background: #e0e7ff;
      transform: translateY(-2px);
    }
    .card.selected {
      background: #2563eb;
      color: white;
      border-color: #1e40af;
      font-weight: 600;
    }
    .button-primary {
      background-color: #2563eb;
      color: white;
      padding: 12px 24px;
      font-weight: 600;
      border-radius: 10px;
      box-shadow: 0 4px 10px rgba(37, 99, 235, 0.3);
      transition: background-color 0.2s ease-in-out;
      border: none;
      cursor: pointer;
    }
    .button-primary:disabled {
      background-color: #9ca3af;
      cursor: not-allowed;
      box-shadow: none;
    }
    .button-primary:hover:not(:disabled) {
      background-color: #1e40af;
    }
    ul.strategy-list {
      list-style: disc inside;
      padding-left: 0;
      margin: 0;
    }
    ul.strategy-list li {
      margin-bottom: 6px;
    }
    .result {
      background: #e0f2fe;
      border: 1px solid #60a5fa;
      padding: 20px;
      border-radius: 12px;
      text-align: center;
    }
    .outcome-fairer {
      color: #16a34a;
      font-weight: 700;
      font-size: 1.25rem;
    }
    .outcome-worse {
      color: #dc2626;
      font-weight: 700;
      font-size: 1.25rem;
    }
    .outcome-same {
      color: #ca8a04;
      font-weight: 700;
      font-size: 1.25rem;
    }
  </style>
</head>
<body>
  <div class="container">
    <!-- Screens -->
    <div id="welcome-screen" class="screen">
      <h1 class="text-3xl font-bold text-center mb-6">Income Inequality Game</h1>
      <p class="text-center mb-8">
        Choose economic policies that either reduce or increase income inequality.
        See how your choices affect the income gap in society.
      </p>
      <button id="start-btn" class="button-primary mx-auto block">Start Game</button>
    </div>

    <div id="policy-selection-screen" class="screen hidden">
      <h2 class="text-2xl font-semibold mb-4 text-center">Select Policies</h2>
      <p class="text-center mb-6">
        Pick one or more policies you think will impact income inequality.
      </p>

      <div class="grid grid-cols-1 md:grid-cols-2 gap-6 mb-8">
        <!-- Closing Gap -->
        <div>
          <h3 class="font-semibold mb-2">Policies That Reduce Inequality</h3>
          <div id="reduce-gap-policies">
            <!-- Cards inserted by JS -->
          </div>
        </div>
        <!-- Increasing Gap -->
        <div>
          <h3 class="font-semibold mb-2">Policies That Increase Inequality</h3>
          <div id="increase-gap-policies">
            <!-- Cards inserted by JS -->
          </div>
        </div>
      </div>

      <button id="run-btn" class="button-primary mx-auto block" disabled>Run Simulation</button>
    </div>

    <div id="results-screen" class="screen hidden">
      <h2 class="text-2xl font-semibold mb-4 text-center">Simulation Results</h2>
      <div class="result mb-6">
        <p>Initial Gini Coefficient: <span id="initial-gini"></span></p>
        <p>Final Gini Coefficient: <span id="final-gini"></span></p>
        <p id="outcome-message" class="mt-4"></p>
      </div>
      <button id="play-again-btn" class="button-primary mx-auto block">Play Again</button>
    </div>
  </div>

<script>
  const NUM_PEOPLE = 1000;
  const BASE_INCOME = 10000;
  const MAX_INCOME_MULTIPLIER = 10;

  // Generate initial skewed income distribution
  function generateIncomeDistribution() {
    let incomes = [];
    for (let i = 0; i < NUM_PEOPLE; i++) {
      // Exponential distribution for inequality
      const income = BASE_INCOME * Math.exp(Math.random() * Math.log(MAX_INCOME_MULTIPLIER));
      incomes.push(income);
    }
    incomes.sort((a,b) => a - b);
    return incomes;
  }

  // Calculate Gini coefficient
  function calculateGini(incomes) {
    const n = incomes.length;
    if (n <= 1) return 0;

    const total = incomes.reduce((a,b) => a+b, 0);
    if (total === 0) return 0;

    let sumDiff = 0;
    for (let i = 0; i < n; i++) {
      for (let j = 0; j < n; j++) {
        sumDiff += Math.abs(incomes[i] - incomes[j]);
      }
    }
    return sumDiff / (2 * n * n * (total/n));
  }

  // Policies definitions
  // Each function takes an income array and returns a new array after applying effect
  const policies = {
    // Reducing inequality
    'progressive-tax': (incomes) => {
      const taxHigh = 0.3;
      const taxMid = 0.1;
      const redistributionPortion = 0.2;
      let newIncomes = incomes.slice();
      let totalTax = 0;

      newIncomes = newIncomes.map(income => {
        if (income > BASE_INCOME * 5) {
          const tax = income * taxHigh;
          totalTax += tax;
          return income - tax;
        } else if (income > BASE_INCOME * 2) {
          const tax = income * taxMid;
          totalTax += tax;
          return income - tax;
        }
        return income;
      });

      const redistributionAmount = totalTax * redistributionPortion / (NUM_PEOPLE * 0.6);
      for(let i=0; i < newIncomes.length * 0.6; i++) {
        newIncomes[i] += redistributionAmount;
      }
      newIncomes.sort((a,b) => a - b);
      return newIncomes;
    },

    'universal-basic-income': (incomes) => {
      const ubi = 1500;
      let newIncomes = incomes.map(i => i + ubi);
      newIncomes.sort((a,b) => a - b);
      return newIncomes;
    },

    'education-investment': (incomes) => {
      let newIncomes = incomes.slice();
      const boost = 0.15;
      for(let i=0; i < newIncomes.length * 0.7; i++) {
        newIncomes[i] *= (1 + boost);
      }
      newIncomes.sort((a,b) => a - b);
      return newIncomes;
    },

    'minimum-wage-increase': (incomes) => {
      let newIncomes = incomes.slice();
      const minWage = BASE_INCOME * 1.25;
      for(let i=0; i < newIncomes.length; i++) {
        if(newIncomes[i] < minWage) newIncomes[i] = minWage;
      }
      newIncomes.sort((a,b) => a - b);
      return newIncomes;
    },

    'wealth-tax': (incomes) => {
      let newIncomes = incomes.slice();
      const wealthTax = 0.05;
      const redistributionPortion = 0.25;
      let totalTax = 0;
      const top5PercentIndex = Math.floor(newIncomes.length * 0.95);

      for(let i=top5PercentIndex; i < newIncomes.length; i++) {
        const tax = newIncomes[i] * wealthTax;
        newIncomes[i] -= tax;
        totalTax += tax;
      }

      const redistributionAmount = totalTax * redistributionPortion / (NUM_PEOPLE * 0.5);
      for(let i=0; i < newIncomes.length * 0.5; i++) {
        newIncomes[i] += redistributionAmount;
      }

      newIncomes.sort((a,b) => a - b);
      return newIncomes;
    },

    // Increasing inequality
    'deregulation': (incomes) => {
      let newIncomes = incomes.slice();
      const topBoost = 0.25;
      const bottomDrop = 0.05;

      for(let i=0; i < newIncomes.length; i++) {
        if(i >= newIncomes.length * 0.8) {
          newIncomes[i] *= (1 + topBoost);
        } else if(i < newIncomes.length * 0.2) {
          newIncomes[i] *= (1 - bottomDrop);
          if(newIncomes[i] < BASE_INCOME * 0.7) newIncomes[i] = BASE_INCOME * 0.7;
        }
      }
      newIncomes.sort((a,b) => a - b);
      return newIncomes;
    },

    'cutting-social-welfare': (incomes) => {
      let newIncomes = incomes.slice();
      const cutPercent = 0.15;

      // Hit bottom 50% hardest
      for(let i=0; i < newIncomes.length * 0.5; i++) {
        newIncomes[i] *= (1 - cutPercent);
        if(newIncomes[i] < BASE_INCOME * 0.5) newIncomes[i] = BASE_INCOME * 0.5;
      }
      newIncomes.sort((a,b) => a - b);
      return newIncomes;
    },

    'flat-tax': (incomes) => {
      let newIncomes = incomes.slice();
      const taxRate = 0.15;

      newIncomes = newIncomes.map(income => income * (1 - taxRate));
      newIncomes.sort((a,b) => a - b);
      return newIncomes;
    }
  };

  // Policies metadata to display cards
  const reduceGapPolicies = [
    {id: 'progressive-tax', name: 'Progressive Taxation', description: 'Higher taxes on wealthy redistribute to poorer.'},
    {id: 'universal-basic-income', name: 'Universal Basic Income', description: 'Cash payments to all citizens.'},
    {id: 'education-investment', name: 'Education Investment', description: 'Boosts earnings potential of lower incomes.'},
    {id: 'minimum-wage-increase', name: 'Minimum Wage Increase', description: 'Raises the lowest wages.'},
    {id: 'wealth-tax', name: 'Wealth Tax', description: 'Tax on richest wealth redistributed.'},
  ];

  const increaseGapPolicies = [
    {id: 'deregulation', name: 'Deregulation', description: 'Benefits top earners, lowers bottom incomes.'},
    {id: 'cutting-social-welfare', name: 'Cutting Social Welfare', description: 'Reduces support for low income earners.'},
    {id: 'flat-tax', name: 'Flat Tax', description: 'Same tax rate for everyone, can increase inequality.'}
  ];

  // DOM Elements
  const screens = {
    welcome: document.getElementById('welcome-screen'),
    policySelection: document.getElementById('policy-selection-screen'),
    results: document.getElementById('results-screen')
  };

  const startBtn = document.getElementById('start-btn');
  const runBtn = document.getElementById('run-btn');
  const playAgainBtn = document.getElementById('play-again-btn');
  const initialGiniSpan = document.getElementById('initial-gini');
  const finalGiniSpan = document.getElementById('final-gini');
  const outcomeMessageEl = document.getElementById('outcome-message');

  const reduceGapContainer = document.getElementById('reduce-gap-policies');
  const increaseGapContainer = document.getElementById('increase-gap-policies');

  let selectedPolicies = new Set();

  function createPolicyCard(policy) {
    const div = document.createElement('div');
    div.className = 'card';
    div.dataset.id = policy.id;

    div.innerHTML = `<h4 class="font-semibold mb-1">${policy.name}</h4><p>${policy.description}</p>`;
    div.addEventListener('click', () => {
      if(selectedPolicies.has(policy.id)) {
        selectedPolicies.delete(policy.id);
        div.classList.remove('selected');
      } else {
        selectedPolicies.add(policy.id);
        div.classList.add('selected');
      }
      runBtn.disabled = selectedPolicies.size === 0;
    });
    return div;
  }

  function showScreen(screen) {
    Object.values(screens).forEach(s => s.classList.add('hidden'));
    screen.classList.remove('hidden');
  }

  function runSimulation() {
    let incomes = generateIncomeDistribution();
    const initialGini = calculateGini(incomes);
    let resultIncomes = incomes.slice();

    selectedPolicies.forEach(id => {
      if(policies[id]) {
        resultIncomes = policies[id](resultIncomes);
      }
    });

    const finalGini = calculateGini(resultIncomes);

    initialGiniSpan.textContent = initialGini.toFixed(3);
    finalGiniSpan.textContent = finalGini.toFixed(3);

    const diff = initialGini - finalGini;
    if(diff > 0.02) {
      outcomeMessageEl.textContent = 'Income inequality DECREASED. The gap has narrowed.';
      outcomeMessageEl.className = 'outcome-fairer';
    } else if(diff < -0.02) {
      outcomeMessageEl.textContent = 'Income inequality INCREASED. The gap has widened.';
      outcomeMessageEl.className = 'outcome-worse';
    } else {
      outcomeMessageEl.textContent = 'Income inequality stayed about the SAME.';
      outcomeMessageEl.className = 'outcome-same';
    }

    showScreen(screens.results);
  }

  // Initialization: add policy cards
  reduceGapPolicies.forEach(policy => {
    reduceGapContainer.appendChild(createPolicyCard(policy));
  });
  increaseGapPolicies.forEach(policy => {
    increaseGapContainer.appendChild(createPolicyCard(policy));
  });

  // Event Listeners
  startBtn.addEventListener('click', () => {
    showScreen(screens.policySelection);
  });

  runBtn.addEventListener('click', () => {
    runSimulation();
  });

  playAgainBtn.addEventListener('click', () => {
    selectedPolicies.clear();
    runBtn.disabled = true;

    // Clear selected styling
    document.querySelectorAll('.card.selected').forEach(el => el.classList.remove('selected'));

    showScreen(screens.policySelection);
  });

  // Show welcome on load
  showScreen(screens.welcome);
</script>
</body>
</html>
