
> 舒适的使用Latex



**配置文件(json) :**

```json
[    
    /*
    
    trigger：触发此片段的文本。
    replacement：要替换的文本 trigger和。
    options： 见下文。
    description（可选）：此片段的描述。
    priority（可选）：此片段的优先级。 默认为 0。优先级较高的代码段首先运行。 可以为负。

选项

    m：数学模式。 仅在 math 中运行此代码段
    t：文本模式。 仅在数学之外运行此代码段
    A： 汽车。 键入触发器后立即展开此代码段。 如果省略，则 Tab必须按下键才能展开代码段
    r: 正则表达式。 这 trigger将被视为正则表达式
    w: 单词边界。 仅当触发器前面（和后面）有单词定界符时才运行此代码段，例如 ., ,， 或者 -.

写入 光标跳转到的制表位 通过在“$0”、“$1”等处 replacement. 
    */
// Self
    {trigger: "__", replacement: "__", options: "__"},
    //t模式_非服务math
    {trigger: "dl", replacement: "\n> [!dl定理] \n> $0", options: "t"},
    {trigger: "yl", replacement: "\n> [!yl引理] \n> $0", options: "t"},   
    {trigger: "dy", replacement: "\n> [!dy定义] \n> $0", options: "t"},   
    {trigger: "zm", replacement: "\n> [!证明] \n> $0", options: "t"},  
    {trigger: "tm", replacement: "### 题目\n\n#### 提示\n#### 答案\n", options: "t"}, 
    
    //rt模式
        //变量,常数,...
    {trigger: "([A-Za-z])(\\d)", replacement: "$[[0]]_{[[1]]}$", options: "rt"},
        //函数
    {trigger: "f([A-Za-z])", replacement: "$[[0]](${0:x})$$1", options: "rt"},
    {trigger: "f2([A-Za-z])", replacement: "[[0]](${0:x},${1:y})$2", options: "rm"},
    {trigger: "f3([A-Za-z])", replacement: "[[0]](${0:x},${1:y},${2:z})$3", options: "rm"},
        //函数名,集合,变量,常数,...
    {trigger: "x([A-Za-z])", replacement: "$[[0]]$$0", options: "rt"},
    {trigger: "([A-Za-z])...", replacement: "$[[0]]_1,\\dots,[[0]]_{${0:n}}$$1", options: "rt"},

    //t模式
    {trigger: "ml", replacement: "$$0$", options: "tA"},
    {trigger: "ml", replacement: "$$0$", options: "t"},
    {trigger: "sml", replacement: "$\\displaystyle{$0}$", options: "tA"},
    {trigger: "sml", replacement: "$\\displaystyle{$0}$", options: "t"},
    {trigger: "mb", replacement: "$$\n$0\n$$", options: "t"},
    {trigger: "f", replacement: "$f$$0", options: "t"},
    {trigger: "(i)", replacement: "$(i).$$0", options: "t"},
    {trigger: "(ii)", replacement: "$(ii).$$0", options: "t"},
    {trigger: "(iii)", replacement: "$(iii).$$0", options: "t"},
    {trigger: "[]", replacement: "$[${0:a},${1:b}]$$2", options: "t"},
    {trigger: "()", replacement: "$(${0:a},${1:b})$$2", options: "t"},
    {trigger: "yf", replacement: "$y=f(${0:x})$$1", options: "t"},  
    
    //rm模式
    {trigger: "([A-Za-z])(\\d)", replacement: "[[0]]_{[[1]]}$0", options: "rm"},//变量,常数,...
    {trigger: "f([A-Za-z])", replacement: "[[0]](${0:x})$1", options: "rm"},//函数
    {trigger: "f([A-Za-z])'", replacement: "[[0]]'(${0:x})$1", options: "rm"},//一阶导函数
    {trigger: "f([A-Za-z])''", replacement: "[[0]]\'\'(${0:x})$1", options: "rm"},//二阶导函数
    {trigger: "f([A-Za-z])'''", replacement: "[[0]]^{(${0:n})}(${1:x})$2", options: "rm"},//n阶导函数

    //简化
    {trigger: "[]", replacement: "[${0:a},${1:b}]$2", options: "m"},
    {trigger: "()", replacement: "(${0:a},${1:b})$2", options: "m"},
    {trigger: "  ", replacement: "~~$0", options: "m"},
    {trigger: ",", replacement: "~,~$0", options: "m"},
    {trigger: "...", replacement: "\\cdots", options: "m"},
    {trigger: ".", replacement: "\\cdot", options: "m"},
    {trigger: "\\3", replacement: "\\vartriangle", options: "m"},    
    {trigger: "tor", replacement: "~~\\text{or}~~$0", options: "m"}, 
    {trigger: "tand", replacement: "~~\\text{and}~~$0", options: "m"}, 
    {trigger: "tbut", replacement: "~~\\text{but}~~$0", options: "m"}, 
    {trigger: "{}", replacement: " \\{$0\\}", options: "m"},
    {trigger: "~", replacement: "\\sim  ", options: "m"},
    {trigger: "+-", replacement: "\\pm  ", options: "m"},

        //特殊公式名
        {trigger: "sin", replacement: "\\sin^{$0}{${1:\\alpha}}$2", options: "m"},
        {trigger: "cos", replacement: "\\cos^{$0}{${1:\\alpha}}$2", options: "m"},
        {trigger: "tan", replacement: "\\tan^{$0}{${1:\\alpha}}$2", options: "m"},
        {trigger: "sec", replacement: "\\sec^{$0}{${1:\\alpha}}$2", options: "m"},
        {trigger: "cot", replacement: "\\cot^{$0}{${1:\\alpha}}$2", options: "m"},
        {trigger: "csc", replacement: "\\csc^{$0}{${1:\\alpha}}$2", options: "m"},
        {trigger: "cot", replacement: "\\cot^{$0}{${1:\\alpha}}$2", options: "m"},
        {trigger: "cot", replacement: "\\cot^{$0}{${1:\\alpha}}$2", options: "m"},
        {trigger: "cot", replacement: "\\cot^{$0}{${1:\\alpha}}$2", options: "m"},
        {trigger: "cot", replacement: "\\cot^{$0}{${1:\\alpha}}$2", options: "m"},
    
    //符号
    {trigger: "==", replacement: "\\equiv  $0", options: "m"},
    {trigger: "<==>", replacement: "\\Longleftrightarrow  $0", options: "m"},
    {trigger: "==>", replacement: "\\Longrightarrow  $0", options: "m"},
    {trigger: "<==", replacement: "\\Longleftarrow  $0", options: "m"},
    {trigger: "!=", replacement: "\\neq  $0", options: "m"},
    {trigger: ">=", replacement: "\\geq  $0", options: "m"},
    {trigger: "<=", replacement: "\\leq  $0", options: "m"},
    {trigger: "in", replacement: "\\in  $0", options: "m"},
    {trigger: "up", replacement: "^{$0}$1", options: "Am"},
    {trigger: "down", replacement: "_{$0}$1", options: "Am"}, 
    {trigger: "*", replacement: "\\times", options: "m"}, 
    
    	//集合符号
    {trigger: "\\<", replacement: "\\subset  $0", options: "m"}, 
    {trigger: "\\>", replacement: "\\supset  $0", options: "m"}, 
    {trigger: "\\n", replacement: "\\cap  $0", options: "m"}, 
	{trigger: "\\N", replacement: "\\bigcap_{$0}^{$1}$2", options: "m"}, 
    {trigger: "\\u", replacement: "\\cup  $0", options: "m"},
	{trigger: "\\U", replacement: "\\bigcup_{$0}^{$1}$2", options: "m"},
            //数的集合符号
    {trigger: "mR", replacement: "\\mathbb{R}", options: "m"},
    {trigger: "mZ", replacement: "\\mathbb{Z}", options: "m"},
        //微积分符号
    {trigger: "lim", replacement: "\\lim_{ ${0:x} \\to ${1:\\infty} } $2", options: "m"},
    {trigger: "int", replacement: "\\int_{${0:a}}^{${1:b}} $2", options: "m"},
    {trigger: "sum", replacement: "\\sum_{${0:i=1}}^{${1:n}} $2", options: "m"},
    {trigger: "8", replacement: "\\infty  $0", options: "m"},//8反转一下,就是无穷符号
    {trigger: "/", replacement: "\\frac{$0}{$1}$2", options: "m"},
        //逻辑符号
    {trigger: "all", replacement: "\\forall  $0", options: "m"},
    {trigger: "exists", replacement: "\\exists  $0", options: "m"},
    {trigger: "or", replacement: "\\lor  $0", options: "m"},
    {trigger: "and", replacement: "\\land  $0", options: "m"},
    {trigger: "not", replacement: "\\lnot  $0", options: "m"},

    //其他
    {trigger: "style", replacement: "\\displaystyle  $0", options: "m"}, 
    {trigger: "begin", replacement: "\\begin{$0}\n$2\n\\end{$1}", options: "m"},
    {trigger: "begina", replacement: "\\begin{align}\n$0\n\\end{align}", options: "m"},
    {trigger: "beginc", replacement: "\\begin{cases}\n$0\n\\end{cases}", options: "m"},

    
    //希腊符号
    {trigger: "@e", replacement: "\\xi", options: "tmA"},
    {trigger: "@o", replacement: "\\sigma", options: "tmA"},
    {trigger: "@3", replacement: "\\varepsilon", options: "tmA"},
    {trigger: "@6", replacement: "\\delta", options: "tmA"},
    {trigger: "@r", replacement: "\\lambda", options: "tmA"},
    {trigger: "@a", replacement: "\\alpha", options: "tmA"},
    {trigger: "@b", replacement: "\\beta", options: "tmA"},   
    {trigger: "@d", replacement: "\\partial", options: "tmA"},    
    {trigger: "@p", replacement: "\\rho", options: "tmA"},   
    {trigger: "@O", replacement: "\\Omega", options: "mA"},   

    

    
    {trigger: "__", replacement: "__", options: "__"},
    {trigger: "__", replacement: "__", options: "__"},
    {trigger: "__", replacement: "__", options: "__"},
    {trigger: "__", replacement: "__", options: "__"},
    {trigger: "__", replacement: "__", options: "__"},
    {trigger: "__", replacement: "__", options: "__"},
    {trigger: "__", replacement: "__", options: "__"},
    {trigger: "__", replacement: "__", options: "__"},
    {trigger: "__", replacement: "__", options: "__"},

    /*
    // Math mode
    {trigger: "ml", replacement: "$$0$", options: "tA"},
    {trigger: "mb", replacement: "$$\n$0\n$$", options: "tAw"},
    {trigger: "beg", replacement: "\\begin{$0}\n$1\n\\end{$0}", options: "mA"},


    // Dashes
    // {trigger: "--", replacement: "–", options: "tA"},
    // {trigger: "–-", replacement: "—", options: "tA"},
    // {trigger: "—-", replacement: "---", options: "tA"},


    // Greek letters
    {trigger: "@a", replacement: "\\alpha", options: "mA"},
    {trigger: "@A", replacement: "\\alpha", options: "mA"},
    {trigger: "@b", replacement: "\\beta", options: "mA"},
    {trigger: "@B", replacement: "\\beta", options: "mA"},
    {trigger: "@c", replacement: "\\chi", options: "mA"},
    {trigger: "@C", replacement: "\\chi", options: "mA"},
    {trigger: "@g", replacement: "\\gamma", options: "mA"},
    {trigger: "@G", replacement: "\\Gamma", options: "mA"},
    {trigger: "@d", replacement: "\\delta", options: "mA"},
    {trigger: "@D", replacement: "\\Delta", options: "mA"},
    {trigger: "@e", replacement: "\\epsilon", options: "mA"},
    {trigger: "@E", replacement: "\\epsilon", options: "mA"},
    {trigger: ":e", replacement: "\\varepsilon", options: "mA"},
    {trigger: ":E", replacement: "\\varepsilon", options: "mA"},
    {trigger: "@z", replacement: "\\zeta", options: "mA"},
    {trigger: "@Z", replacement: "\\zeta", options: "mA"},
    {trigger: "@t", replacement: "\\theta", options: "mA"},
    {trigger: "@T", replacement: "\\Theta", options: "mA"},
    {trigger: "@k", replacement: "\\kappa", options: "mA"},
    {trigger: "@K", replacement: "\\kappa", options: "mA"},
    {trigger: "@l", replacement: "\\lambda", options: "mA"},
    {trigger: "@L", replacement: "\\Lambda", options: "mA"},
    {trigger: "@m", replacement: "\\mu", options: "mA"},
    {trigger: "@M", replacement: "\\mu", options: "mA"},
    {trigger: "@r", replacement: "\\rho", options: "mA"},
    {trigger: "@R", replacement: "\\rho", options: "mA"},
    {trigger: "@s", replacement: "\\sigma", options: "mA"},
    {trigger: "@S", replacement: "\\Sigma", options: "mA"},
    {trigger: "ome", replacement: "\\omega", options: "mA"},
    {trigger: "@o", replacement: "\\omega", options: "mA"},
    {trigger: "@O", replacement: "\\Omega", options: "mA"},
    {trigger: "([^\\\\])(${GREEK}|${SYMBOL})", replacement: "[[0]]\\[[1]]", options: "rmA", description: "Add backslash before greek letters and symbols"},


    // Insert space after greek letters and symbols, etc
    {trigger: "\\\\(${GREEK}|${SYMBOL}|${SHORT_SYMBOL})([A-Za-z])", replacement: "\\[[0]] [[1]]", options: "rmA"},
    {trigger: "\\\\(${GREEK}|${SYMBOL}) sr", replacement: "\\[[0]]^{2}", options: "rmA"},
    {trigger: "\\\\(${GREEK}|${SYMBOL}) cb", replacement: "\\[[0]]^{3}", options: "rmA"},
    {trigger: "\\\\(${GREEK}|${SYMBOL}) rd", replacement: "\\[[0]]^{$0}$1", options: "rmA"},
    {trigger: "\\\\(${GREEK}|${SYMBOL}) hat", replacement: "\\hat{\\[[0]]}", options: "rmA"},
    {trigger: "\\\\(${GREEK}|${SYMBOL}) dot", replacement: "\\dot{\\[[0]]}", options: "rmA"},
    {trigger: "\\\\(${GREEK}|${SYMBOL}) bar", replacement: "\\bar{\\[[0]]}", options: "rmA"},
    {trigger: "\\\\(${GREEK}|${SYMBOL}) vec", replacement: "\\vec{\\[[0]]}", options: "rmA"},
    {trigger: "\\\\(${GREEK}|${SYMBOL}) tilde", replacement: "\\tilde{\\[[0]]}", options: "rmA"},
    {trigger: "\\\\(${GREEK}|${SYMBOL}) und", replacement: "\\underline{\\[[0]]}", options: "rmA"},
    {trigger: "\\\\(${GREEK}),\\.", replacement: "\\boldsymbol{\\[[0]]}", options: "rmA"},
    {trigger: "\\\\(${GREEK})\\.,", replacement: "\\boldsymbol{\\[[0]]}", options: "rmA"},


    // Operations
    {trigger: "te", replacement: "\\text{$0}", options: "m"},
    {trigger: "text", replacement: "\\text{$0}", options: "mA"},
    {trigger: "bf", replacement: "\\mathbf{$0}", options: "mA"},
    {trigger: "sr", replacement: "^{2}", options: "mA"},
    {trigger: "cb", replacement: "^{3}", options: "mA"},
    {trigger: "rd", replacement: "^{$0}$1", options: "mA"},
    {trigger: "_", replacement: "_{$0}$1", options: "mA"},
    {trigger: "sts", replacement: "_\\text{$0}", options: "rmA"},
    {trigger: "sq", replacement: "\\sqrt{ $0 }$1", options: "mA"},
    {trigger: "//", replacement: "\\frac{$0}{$1}$2", options: "mA"},
    {trigger: "ee", replacement: "e^{ $0 }$1", options: "mA"},
    {trigger: "rm", replacement: "\\mathrm{$0}$1", options: "mA"},
    {trigger: "conj", replacement: "^{*}", options: "mA"},
    {trigger: "trace", replacement: "\\mathrm{Tr}", options: "mA"},
    {trigger: "det", replacement: "\\det", options: "mA"},
    {trigger: "re", replacement: "\\mathrm{Re}", options: "mA"},
    {trigger: "im", replacement: "\\mathrm{Im}", options: "mA"},

    {trigger: "([a-zA-Z]),\\.", replacement: "\\mathbf{[[0]]}", options: "rmA"},
    {trigger: "([a-zA-Z])\\.,", replacement: "\\mathbf{[[0]]}", options: "rmA"},
    {trigger: "([A-Za-z])(\\d)", replacement: "[[0]]_{[[1]]}", options: "rmA", description: "Auto letter subscript", priority: -1},
    {trigger: "([A-Za-z])_(\\d\\d)", replacement: "[[0]]_{[[1]]}", options: "rmA"},
    {trigger: "\\hat{([A-Za-z])}(\\d)", replacement: "hat{[[0]]}_{[[1]]}", options: "rmA"},
    {trigger: "\\\\mathbf{([A-Za-z])}(\\d)", replacement: "\\mathbf{[[0]]}_{[[1]]}", options: "rmA"},
    {trigger: "\\\\vec{([A-Za-z])}(\\d)", replacement: "\\vec{[[0]]}_{[[1]]}", options: "rmA"},
    {trigger: "([a-zA-Z])bar", replacement: "\\bar{[[0]]}", options: "rmA"},
    {trigger: "([a-zA-Z])hat", replacement: "\\hat{[[0]]}", options: "rmA"},
    {trigger: "([a-zA-Z])ddot", replacement: "\\ddot{[[0]]}", options: "rmA", priority: 3},
    {trigger: "([a-zA-Z])dot", replacement: "\\dot{[[0]]}", options: "rmA", priority: 1},
    {trigger: "([a-zA-Z])vec", replacement: "\\vec{[[0]]}", options: "rmA"},
    {trigger: "([a-zA-Z])tilde", replacement: "\\tilde{[[0]]}", options: "rmA"},
    {trigger: "([a-zA-Z])und", replacement: "\\underline{[[0]]}", options: "rmA"},
    {trigger: "bar", replacement: "\\bar{$0}$1", options: "mA"},
    {trigger: "hat", replacement: "\\hat{$0}$1", options: "mA"},
    {trigger: "dot", replacement: "\\dot{$0}$1", options: "mA"},
    {trigger: "ddot", replacement: "\\ddot{$0}$1", options: "mA", priority: 2},
    {trigger: "vec", replacement: "\\vec{$0}$1", options: "mA"},
    {trigger: "tilde", replacement: "\\tilde{$0}$1", options: "mA"},
    {trigger: "und", replacement: "\\underline{$0}$1", options: "mA"},

    {trigger: "([^\\\\])(arcsin|arccos|arctan|arccot|arccsc|arcsec|sin|cos|tan|cot|csc)", replacement: "[[0]]\\[[1]]", options: "rmA"},
    {trigger: "\\\\(arcsin|arccos|arctan|arccot|arccsc|arcsec|sin|cos|tan|cot|csc)([A-Za-gi-z])", replacement: "\\[[0]] [[1]]", options: "rmA"}, // Insert space after trig funcs. Skips letter "h" to allow sinh, cosh, etc.
    {trigger: "\\\\(arcsinh|arccosh|arctanh|arccoth|arcsch|arcsech|sinh|cosh|tanh|coth|csch)([A-Za-z])", replacement: "\\[[0]] [[1]]", options: "rmA"}, // Insert space after trig funcs
    //{trigger: "\\\\(neq|geq|leq|gg|ll|sim)([0-9]+)", replacement: "\\[[0]] [[1]]", options: "rmA"}, // Insert space after inequality symbols


    // Visual operations
    {trigger: "U", replacement: "\\underbrace{ ${VISUAL} }_{ $0 }", options: "mA"},
    {trigger: "B", replacement: "\\underset{ $0 }{ ${VISUAL} }", options: "mA"},
    {trigger: "C", replacement: "\\cancel{ ${VISUAL} }", options: "mA"},
    {trigger: "K", replacement: "\\cancelto{ $0 }{ ${VISUAL} }", options: "mA"},
    {trigger: "S", replacement: "\\sqrt{ ${VISUAL} }", options: "mA"},



    // Symbols
    {trigger: "ooo", replacement: "\\infty", options: "mA"},
    {trigger: "sum", replacement: "\\sum", options: "mA"},
    {trigger: "prod", replacement: "\\prod", options: "mA"},
    {trigger: "lim", replacement: "\\lim_{ ${0:n} \\to ${1:\\infty} } $2", options: "mA"},
    {trigger: "([^\\\\])pm", replacement: "[[0]]\\pm", options: "rm"},
    {trigger: "([^\\\\])mp", replacement: "[[0]]\\mp", options: "rm"},
    {trigger: "+-", replacement: "\\pm", options: "mA"},
    {trigger: "-+", replacement: "\\mp", options: "mA"},
    {trigger: "...", replacement: "\\dots", options: "mA"},
    {trigger: "<->", replacement: "\\leftrightarrow ", options: "mA"},
    {trigger: "->", replacement: "\\to", options: "mA"},
    {trigger: "!>", replacement: "\\mapsto", options: "mA"},
    {trigger: "invs", replacement: "^{-1}", options: "mA"},
    {trigger: "\\\\\\", replacement: "\\setminus", options: "mA"},
    {trigger: "||", replacement: "\\mid", options: "mA"},
    {trigger: "and", replacement: "\\cap", options: "mA"},
    {trigger: "orr", replacement: "\\cup", options: "mA"},
    {trigger: "inn", replacement: "\\in", options: "mA"},
    {trigger: "\\subset eq", replacement: "\\subseteq", options: "mA"},
    {trigger: "set", replacement: "\\{ $0 \\}$1", options: "mA"},
    {trigger: "=>", replacement: "\\implies", options: "mA"},
    {trigger: "=<", replacement: "\\impliedby", options: "mA"},
    {trigger: "iff", replacement: "\\iff", options: "mA"},
    {trigger: "e\\xi sts", replacement: "\\exists", options: "mA", priority: 1},
    {trigger: "===", replacement: "\\equiv", options: "mA"},
    {trigger: "Sq", replacement: "\\square", options: "mA"},
    {trigger: "!=", replacement: "\\neq", options: "mA"},
    {trigger: ">=", replacement: "\\geq", options: "mA"},
    {trigger: "<=", replacement: "\\leq", options: "m"},
    {trigger: ">>", replacement: "\\gg", options: "mA"},
    // {trigger: "<<", replacement: "\\ll", options: "mA"},
    {trigger: "~~", replacement: "\\sim", options: "mA"},
    {trigger: "\\sim ~", replacement: "\\approx", options: "mA"},
    {trigger: "prop", replacement: "\\propto", options: "mA"},
    {trigger: "nabl", replacement: "\\nabla", options: "mA"},
    {trigger: "del", replacement: "\\nabla", options: "mA"},
    {trigger: "xx", replacement: "\\times", options: "mA"},
    {trigger: "**", replacement: "\\cdot", options: "mA"},
    {trigger: "para", replacement: "\\parallel", options: "mA"},


    {trigger: "xnn", replacement: "x_{n}", options: "mA"},
    {trigger: "xii", replacement: "x_{i}", options: "mA"},
    {trigger: "xjj", replacement: "x_{j}", options: "mA"},
    {trigger: "xp1", replacement: "x_{n+1}", options: "mA"},
    {trigger: "ynn", replacement: "y_{n}", options: "mA"},
    {trigger: "yii", replacement: "y_{i}", options: "mA"},
    {trigger: "yjj", replacement: "y_{j}", options: "mA"},


    // {trigger: "mcal", replacement: "\\mathcal{$0}$1", options: "mA"},
    // {trigger: "mbb", replacement: "\\mathbb{$0}$1", options: "mA"},
    // {trigger: "ell", replacement: "\\ell", options: "mA"},
    // {trigger: "lll", replacement: "\\ell", options: "mA"},
    // {trigger: "LL", replacement: "\\mathcal{L}", options: "mA"},
    // {trigger: "HH", replacement: "\\mathcal{H}", options: "mA"},
    // {trigger: "CC", replacement: "\\mathbb{C}", options: "mA"},
    // {trigger: "RR", replacement: "\\mathbb{R}", options: "mA"},
    // {trigger: "ZZ", replacement: "\\mathbb{Z}", options: "mA"},
    // {trigger: "NN", replacement: "\\mathbb{N}", options: "mA"},
    // {trigger: "II", replacement: "\\mathbb{1}", options: "mA"},
    // {trigger: "\\mathbb{1}I", replacement: "\\hat{\\mathbb{1}}", options: "mA"},
    // {trigger: "AA", replacement: "\\mathcal{A}", options: "mA"},
    // {trigger: "BB", replacement: "\\mathbf{B}", options: "mA"},
    // {trigger: "EE", replacement: "\\mathbf{E}", options: "mA"},



    // Unit vectors
    // {trigger: ":i", replacement: "\\mathbf{i}", options: "mA"},
    // {trigger: ":j", replacement: "\\mathbf{j}", options: "mA"},
    // {trigger: ":k", replacement: "\\mathbf{k}", options: "mA"},
    // {trigger: ":x", replacement: "\\hat{\\mathbf{x}}", options: "mA"},
    // {trigger: ":y", replacement: "\\hat{\\mathbf{y}}", options: "mA"},
    // {trigger: ":z", replacement: "\\hat{\\mathbf{z}}", options: "mA"},



    // Derivatives
    // {trigger: "par", replacement: "\\frac{ \\partial ${0:y} }{ \\partial ${1:x} } $2", options: "m"},
    // {trigger: "pa2", replacement: "\\frac{ \\partial^{2} ${0:y} }{ \\partial ${1:x}^{2} } $2", options: "mA"},
    // {trigger: "pa3", replacement: "\\frac{ \\partial^{3} ${0:y} }{ \\partial ${1:x}^{3} } $2", options: "mA"},
    // {trigger: "pa([A-Za-z])([A-Za-z])", replacement: "\\frac{ \\partial [[0]] }{ \\partial [[1]] } ", options: "rm"},
    // {trigger: "pa([A-Za-z])([A-Za-z])([A-Za-z])", replacement: "\\frac{ \\partial^{2} [[0]] }{ \\partial [[1]] \\partial [[2]] } ", options: "rm"},
    // {trigger: "pa([A-Za-z])([A-Za-z])2", replacement: "\\frac{ \\partial^{2} [[0]] }{ \\partial [[1]]^{2} } ", options: "rmA"},
    // {trigger: "de([A-Za-z])([A-Za-z])", replacement: "\\frac{ d[[0]] }{ d[[1]] } ", options: "rm"},
    // {trigger: "de([A-Za-z])([A-Za-z])2", replacement: "\\frac{ d^{2}[[0]] }{ d[[1]]^{2} } ", options: "rmA"},
    // {trigger: "ddt", replacement: "\\frac{d}{dt} ", options: "mA"},



    // Integrals
    // {trigger: "oinf", replacement: "\\int_{0}^{\\infty} $0 \\, d${1:x} $2", options: "mA"},
    // {trigger: "infi", replacement: "\\int_{-\\infty}^{\\infty} $0 \\, d${1:x} $2", options: "mA"},
    // {trigger: "dint", replacement: "\\int_{${0:0}}^{${1:\\infty}} $2 \\, d${3:x} $4", options: "mA"},
    // {trigger: "oint", replacement: "\\oint", options: "mA"},
    // {trigger: "iiint", replacement: "\\iiint", options: "mA"},
    // {trigger: "iint", replacement: "\\iint", options: "mA"},
    // {trigger: "int", replacement: "\\int $0 \\, d${1:x} $2", options: "mA"},



    // Physics
    // {trigger: "kbt", replacement: "k_{B}T", options: "mA"},


    // Quantum mechanics
    // {trigger: "hba", replacement: "\\hbar", options: "mA"},
    // {trigger: "dag", replacement: "^{\\dagger}", options: "mA"},
    // {trigger: "o+", replacement: "\\oplus ", options: "mA"},
    // {trigger: "ox", replacement: "\\otimes ", options: "mA"},
    // {trigger: "ot\\mathrm{Im}es", replacement: "\\otimes ", options: "mA"}, // Handle conflict with "im" snippet
    // {trigger: "bra", replacement: "\\bra{$0} $1", options: "mA"},
    // {trigger: "ket", replacement: "\\ket{$0} $1", options: "mA"},
    // {trigger: "brk", replacement: "\\braket{ $0 | $1 } $2", options: "mA"},
    // {trigger: "\\\\bra{([^|]+)\\|", replacement: "\\braket{ [[0]] | $0 ", options: "rmA", description: "Convert bra into braket"},
    // {trigger: "\\\\bra{(.+)}([^ ]+)>", replacement: "\\braket{ [[0]] | $0 ", options: "rmA", description: "Convert bra into braket (alternate)"},
    // {trigger: "outp", replacement: "\\ket{${0:\\psi}} \\bra{${0:\\psi}} $1", options: "mA"},



    // Chemistry
    // {trigger: "pu", replacement: "\\pu{ $0 }", options: "mA"},
    // {trigger: "msun", replacement: "M_{\\odot}", options: "mA"},
    // {trigger: "solm", replacement: "M_{\\odot}", options: "mA"},
    // {trigger: "ce", replacement: "\\ce{ $0 }", options: "mA"},
    // {trigger: "iso", replacement: "{}^{${0:4}}_{${1:2}}${2:He}", options: "mA"},
    // {trigger: "hel4", replacement: "{}^{4}_{2}He ", options: "mA"},
    // {trigger: "hel3", replacement: "{}^{3}_{2}He ", options: "mA"},



    // Environments
    // {trigger: "pmat", replacement: "\\begin{pmatrix}\n$0\n\\end{pmatrix}", options: "mA"},
    // {trigger: "bmat", replacement: "\\begin{bmatrix}\n$0\n\\end{bmatrix}", options: "mA"},
    // {trigger: "Bmat", replacement: "\\begin{Bmatrix}\n$0\n\\end{Bmatrix}", options: "mA"},
    // {trigger: "vmat", replacement: "\\begin{vmatrix}\n$0\n\\end{vmatrix}", options: "mA"},
    // {trigger: "Vmat", replacement: "\\begin{Vmatrix}\n$0\n\\end{Vmatrix}", options: "mA"},
    // {trigger: "case", replacement: "\\begin{cases}\n$0\n\\end{cases}", options: "mA"},
    // {trigger: "align", replacement: "\\begin{align}\n$0\n\\end{align}", options: "mA"},
    // {trigger: "array", replacement: "\\begin{array}\n$0\n\\end{array}", options: "mA"},
    // {trigger: "matrix", replacement: "\\begin{matrix}\n$0\n\\end{matrix}", options: "mA"},



    // Brackets
    {trigger: "avg", replacement: "\\langle $0 \\rangle $1", options: "mA"},
    {trigger: "norm", replacement: "\\lvert $0 \\rvert $1", options: "mA", priority: 1},
    {trigger: "mod", replacement: "|$0|$1", options: "mA"},
    {trigger: "(", replacement: "(${VISUAL})", options: "mA"},
    {trigger: "[", replacement: "[${VISUAL}]", options: "mA"},
    {trigger: "{", replacement: "{${VISUAL}}", options: "mA"},
    {trigger: "(", replacement: "($0)$1", options: "mA"},
    {trigger: "{", replacement: "{$0}$1", options: "mA"},
    {trigger: "[", replacement: "[$0]$1", options: "mA"},
    {trigger: "lr(", replacement: "\\left( $0 \\right) $1", options: "mA"},
    {trigger: "lr|", replacement: "\\left| $0 \\right| $1", options: "mA"},
    {trigger: "lr{", replacement: "\\left\\{ $0 \\right\\} $1", options: "mA"},
    {trigger: "lr[", replacement: "\\left[ $0 \\right] $1", options: "mA"},
    {trigger: "lra", replacement: "\\left< $0 \\right> $1", options: "mA"},



    // Misc
    // {trigger: "tayl", replacement: "${0:f}(${1:x} + ${2:h}) = ${0:f}(${1:x}) + ${0:f}'(${1:x})${2:h} + ${0:f}''(${1:x}) \\frac{${2:h}^{2}}{2!} + \\dots$3", options: "mA"},
    */
]
```
