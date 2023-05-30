# Set theme site

## JavaScript
    const themeSystem=localStorage.getItem("themeSystem")||"light"; // Get the theme from localStorage
    const btn=document.getElementById("btn");

    btn.addEventListener("click",()=>{
        let oldTheme=localStorage.getItem("themeSystem")||"light";
        let newTheme=oldTheme==="light"?"dark":"light"; // Checks if the theme is dark or light and invert
        localStorage.setItem("themeSystem",newTheme) // Set this new theme in the localStorage
        defineTheme(newTheme); // Define the theme in the data-theme and change the button icon
    })

    defineTheme=(theme)=>{
        const dark="<i class='bi bi-moon-stars-fill'></i>";
        const light="<i class='bi bi-brightness-high-fill'></i>";

        document.documentElement.setAttribute("data-theme",theme); // Get the theme from the document

        if(theme==="dark"){
            btn.innerHTML=light;
        }else{
            btn.innerHTML=dark;
        }
    }
    defineTheme(themeSystem);

## Css
    :root{
        --dark: #222;
        --light: #f2f2f2;
        --purple: #9e6aff;
        --purple-hover: #b187ff;
    }

    [data-theme="dark"]{ /* Invert the colors */
        --light: #222;
        --dark: #f2f2f2;
    }
