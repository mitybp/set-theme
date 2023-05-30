# Set theme site

### In script
    const themeSystem=localStorage.getItem("themeSystem")||"light";
    const btn=document.getElementById("btn")

    btn.addEventListener("click",()=>{
        let oldTheme=localStorage.getItem("themeSystem")||"light";
        let newTheme=oldTheme==="light"?"dark":"light";
        localStorage.setItem("themeSystem",newTheme)
        defineTheme(newTheme);
    })

    defineTheme=(theme)=>{
        const dark="<i class='bi bi-moon-stars-fill'></i>";
        const light="<i class='bi bi-brightness-high-fill'></i>";

        document.documentElement.setAttribute("data-theme",theme);

        if(theme==="dark"){
            btn.innerHTML=light;
        }else{
            btn.innerHTML=dark;
        }
    }
    defineTheme(themeSystem);
