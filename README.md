<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Math Budy</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/mathjs/11.8.0/math.min.js"></script>
</head>

<body class="bg-gray-50 text-gray-800 min-h-screen">
  <!-- Navbar -->
  <header class="bg-white shadow p-4 flex justify-between items-center">
    <h1 class="text-2xl font-bold">Math Budy</h1>
    <nav>
      <a href="#" class="text-blue-600 hover:underline">Home</a>
      <a href="#calculator" class="ml-4 text-blue-600 hover:underline">Calculator</a>
    </nav>
  </header>

  <!-- Home Section -->
  <section class="p-8 text-center">
    <h2 class="text-3xl font-semibold mb-4">Welcome to Math Budy</h2>
    <p class="text-lg max-w-xl mx-auto">
      A simple math helper website that can solve basic arithmetic and algebra problems.
    </p>
  </section>

  <!-- Calculator Section -->
  <section id="calculator" class="p-8 bg-white rounded-xl shadow max-w-2xl mx-auto mt-8">
    <h3 class="text-2xl font-semibold mb-4">Math Calculator</h3>
    <input id="expression" type="text" placeholder="Enter expression, e.g. 2x + 3 = 7" class="w-full p-3 border rounded-lg text-lg" />
    <button onclick="solveExpression()" class="mt-4 bg-blue-600 text-white px-4 py-2 rounded-lg hover:bg-blue-700">
      Solve
    </button>
    <div id="output" class="mt-4 text-lg font-medium text-green-600"></div>
  </section>

  <script>
    function solveExpression() {
      const input = document.getElementById('expression').value;
      const output = document.getElementById('output');
      try {
        // If it's an equation like "2x + 3 = 7"
        if (input.includes('=')) {
          const [left, right] = input.split('=').map(side => math.parse(side).toString());
          const solution = math.solve(input, 'x');
          output.innerText = `x = ${solution}`;
        } else {
          const result = math.evaluate(input);
          output.innerText = `Answer: ${result}`;
        }
      } catch (err) {
        output.innerText = `Error: ${err.message}`;
      }
    }
  </script>
</body>

</html>


Your basic Math Budy website is ready! It includes:

A homepage with a welcome message

A math calculator that can solve both arithmetic and algebra (like 2x + 3 = 7)

A clean, mobile-friendly design using Tailwind CSS


Let me know if you want to:

Add step-by-step solving

Include a graphing feature

Support more equations

Deploy it online (free options available)


Want me to turn this into a downloadable file or publish it live?

