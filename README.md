## How to install tailwindcss to blazor project:
1. Go to ".\TailwindBlazor\TailwindBlazor" in CMD and run command:
```
npx tailwindcss init
```

2. The "tailwind.config.js" file will be created. Change it to:
```
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: ['./**/*.{razor,html}'],
  theme: {
    extend: {},
  },
  plugins: [],
}
```

3. Create /Styles/tailwind.css file and change it to: 
```
@tailwind base;
@tailwind components;
@tailwind utilities;
```

4. Add some tailwindcss classes to "Home.razor" component:
```
@page "/"
<PageTitle>Home</PageTitle>
<h1 class="font-extrabold text-5xl">Hello, world!</h1>
Welcome to your new app.
```

5. Add tailwind file to "index.html": 
 ```
<link rel="stylesheet" href="css/tailwind.css" />
```

6. Comment out some code in "NavMenu.razor" that toogles nav menu (bug)
```
<button title="Navigation menu" class="navbar-toggler" @onclick="ToggleNavMenu">
    <span class="navbar-toggler-icon"></span>
</button>

<div class="@NavMenuCssClass nav-scrollable" @onclick="ToggleNavMenu">

</div>
```

7. Run command to build tailwind and listen to changes:
```
npx tailwindcss -i .\Styles\tailwind.css -o .\wwwroot\css\tailwind.css --watch
```
