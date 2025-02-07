computer vision courses overview:
- penn's is more basic and focusing on fundamental, there's lower level technicality
- cs131 is topic based and segmented based on the techniques and usages. It's very heavy in technicality but never dive deep into it, likely to read lot of papers for in depth understanding
- hst582's course on bioimaging is math heavy and too specialised
- 6.801 - in depth fundamental leaning on how machine see things rather than processing or machine learning. This is a robotic course?
- 6.003 - signal processing
- 6.881 - representation and modeling for image processing, technical and structural approach to cv


fundametal: 6.003, penn, linear algebra, calculus. Mostly homework and complimentary papers. 
- calculus + 6.003
1. https://ocw.mit.edu/courses/18-01-calculus-i-single-variable-calculus-fall-2020/
2. https://ocw.mit.edu/courses/18-02-multivariable-calculus-fall-2007/
3. https://ocw.mit.edu/courses/18-075-advanced-calculus-for-engineers-fall-2004
4. https://ocw.mit.edu/courses/6-080-great-ideas-in-theoretical-computer-science-spring-2008/
5. https://ocw.mit.edu/courses/6-003-signals-and-systems-fall-2011/

intermediate: cs131, 6.881, machine learning, AI stuff. Start building projects and contribution to public repo. Research a branch of cv for project development
specialised: hst582, go on as needed to penetrate a field


conclusion to multilingual app:
- target languages: engish, chinese, tamil, bahasa, malay, or variable languages. Prof want to extend to as many languages as possible, while maintaining relative good accuracy. Prioritise Asian languages
- Google translate has the greatest language bank, with many research supporting its performance: Tamil, indonesian, chinese and malay has supporting research for good accuracy
- method of implementations:
    1. app: generating translation files and ship with the app
    2. resources: the resources on the server can be requested with target language and translated on the spot, and get cached. Or the translation can be generated on update, and saved to the database


# PFP
DigitalOcean
Email: blitz.bala@gmail.com
PW: PFPAdmin123$

Zoho (Email Client)
Email: blitz.bala@gmail.com
PW: PFPAdmin123$

Note:
- Can configure up to 5 emails
- Current email configured: admin@pilotsforpilots.org


todos:
- startup the backend and test all the docker images works
- start the frontend and test the annoucement with/without images


# empower
get an online physician with least amount of patient in his management

# bjj
- go for sg2 beginner classes on aug 5 - sept 13
- switch gym to fortitude



# AI healthcare plan
This healthcare plan, do you have template or a database of them to see what is it supposed to look like.
Since LLM perform better with a structured output, you should build a template
In each component of the template, you you supply the model with only relevant information
from the data collected, categorize the data into relevant field for the next stage of processing


- Framework: [i18n](https://www.i18next.com/), [react-i18next](https://react.i18next.com/)
- languages files: `lang/en.json` and `lang/id.json` for english and bahasa indonesia. Mapping a label to respective language text.
e.g. `en.json`
```json
{
    "translation": {
        "greeting": "Hello"
    }
}
```
`id.json`
```json
{
    "translation": {
        "greeting": "Halo"
    }
}
```

- how to use:
assign `t()` function from `i18next` at the top of the file

```js
import i18n from 'i18next';

const t = i18n.t;

// use in plain function
const get_string() => {
    return t("greeting")
}


// use in components
const Body(props) => {
    return <div>t("greeting")</div>
}
```

