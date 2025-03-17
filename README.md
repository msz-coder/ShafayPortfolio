# **Personal Portfolio Website**

A fully responsive **personal portfolio website** to showcase **projects, skills, and experiences**. Built using **React.js**, inspired by the **DeveloperFolio** template, but heavily modified to match **my personal branding, projects, and professional journey**.

- **Date Created**: 10 March 2025  
- **Last Modification Date**: 15 March 2025  
- **Live URL**: [Shafay's Portfolio](https://main.d3va7qg6o6ibvu.amplifyapp.com/) 
- **Original GitHub Repository**: [DeveloperFolio](https://github.com/saadpasta/developerFolio)  
- **Current Repository**: [My Custom Portfolio](https://github.com/msz-coder/Portfolio-V2)  

---

## **Authors**

- [Muhammad Shafay Zulfiqar](m.shafay@dal.ca) - **Developer & Maintainer**  

---

## **Major Modifications from DeveloperFolio**

This portfolio is **not just a clone** of DeveloperFolio, it has undergone **major modifications**:

**Removed Unnecessary Sections**:  
- Blogs, Talks, Podcasts sections **removed** to focus on Projects, Experience, and Contact.  

**Updated UI & Content**:  
- **Replaced all placeholder data** with my actual details.  
- **Customized dark mode styles** and improved responsiveness.  
- **Updated Resume Section** with dynamic resume link.  

**Performance & Code Improvements**:  
- **Refactored components** for better maintainability.  
- **Fixed accessibility issues** (`WCAG guidelines` compliance).  
- **Test cases added** for `components` and `utility functions`.  

---

## **Built With**

This project was built using the following technologies:

- [React.js](https://react.dev/) - **Frontend JavaScript library**  
- [Sass](https://sass-lang.com/) - **CSS Preprocessor for styling**  
- [React Reveal](https://www.react-reveal.com/) - **Animation effects**  
- [React Router](https://reactrouter.com/) - **Client-side routing**  
- [Lottie React](https://github.com/LottieFiles/lottie-react) - **Animation handling**  
- [FontAwesome](https://fontawesome.com/) - **Icons and UI elements**  
- [Jest](https://jestjs.io/) - **Unit testing framework**  
- [React Testing Library](https://testing-library.com/docs/react-testing-library/intro/) - **Component testing**  

---

## **Testing & Mock Files**

🧪 **Comprehensive test cases** were written for multiple components to ensure reliability.

### **Test Files & Mock Data**
📂 **Location**: `src/tests/`  
- `404.test.js` - **Ensures the 404 page renders correctly.**  
- `App.test.js` - **Tests the main app rendering & routing.**  
- `experienceCard.test.js` - **Checks ExperienceCard component rendering.**  
- `Header.test.js` - **Verifies navigation header behavior.**  
- `ToggleSwitch.test.js` - **Ensures dark mode toggle works properly.**  
- `utils.test.js` - **Validates helper utility functions.**  

---

## **Sources Used & Changes Made**

### **Greeting.js**
#### **Issue Fixed: `<a>` tag inside `<button>`**
##### **File Path**: `src/components/Greeting/Greeting.js`
##### **Lines Modified: 49 - 58**
```jsx
<div className="button-greeting-div">
  <Button text="Contact me" href="#contact" />
  {greeting.resumeLink && (
    <a
      href={greeting.resumeLink}
      target="_blank"
      rel="noopener noreferrer"
      className="download-link-button"
    >
      <Button text="View My Resume" />
    </a>
  )}
</div>
```
##### **Original Code**
```jsx
<div className="button-greeting-div">
  <Button text="Contact me" href="#contact" />
  <Button text="View My Resume" newTab={true} />
</div>
```
##### **Changes**
- **How**: Used an `<a>` tag for `resumeLink` instead of nesting `<Button>` inside `<a>`.
- **Why**: Fixed **invalid HTML nesting** (`<a>` inside `<button>` is not valid).
- **How Modified**: Wrapped the `Button` component inside an `<a>` tag with `rel="noopener noreferrer"` for security.

---

### **StartupProject.js**
#### **Issue Fixed: `<ul>` cannot appear inside `<p>`**
##### **File Path**: `src/components/StartupProject/StartupProject.js`
##### **Lines Modified: 55 - 70**
```jsx
{Array.isArray(project.projectDesc) ? (
  <ul>
    {project.projectDesc.map((point, index) =>
      point ? <li key={index}>{point}</li> : null
    )}
  </ul>
) : (
  <p>{project.projectDesc}</p>
)}
```
##### **Original Code**
```jsx
<p>{project.projectDesc}</p>
```
##### **Changes**
- **How**: Checked if `project.projectDesc` is an array, then rendered it inside a `<ul>`.
- **Why**: Fixed **invalid nesting** where `<ul>` was inside `<p>`, which is not allowed.
- **How Modified**: Now correctly displays either a **list** or a **paragraph**.

---

## **Artificial Intelligence Tools Used**

- [ChatGPT](https://openai.com/chatgpt) - **Debugging, Code Review, & Optimization**  
- [GitHub Copilot](https://github.com/features/copilot) - **Code Autocompletion & Refactoring**  

### **Prompt Used on ChatGPT**
```
Fix invalid nesting of <a> inside <button> in my React project.
```
#### **Generated Code**
```jsx
<a
  href={greeting.resumeLink}
  target="_blank"
  rel="noopener noreferrer"
  className="download-link-button"
>
  <Button text="View My Resume" />
</a>
```
##### **Implementation**
- **How**: Implemented in `Greeting.js` to ensure valid HTML structure.
- **Why**: The `<Button>` was originally inside an `<a>`, which is invalid.
- **How Modified**: Used a standalone `<a>` for the resume download button.

---

## **Accessibility Considerations (WCAG Guidelines)**

This website implements **WCAG Guidelines** for accessibility:

**Keyboard Navigation** - Users can navigate all elements using the keyboard.  
**Semantic HTML** - Correct heading levels, `<button>`, `<a>`, `<ul>` elements are used appropriately.  
**Color Contrast** - Dark mode and light mode options enhance readability.  
**ARIA Attributes** - Used `aria-label` for screen readers where necessary.  
**Skip Links** - Added a **skip-to-content link** for screen reader users.  

---

## **Acknowledgments**

- **[Saad Pasta](https://github.com/saadpasta)** for the **DeveloperFolio** template.  
- Inspired by modern **developer portfolios**.  
- Thanks to **OpenAI** and **GitHub Copilot** for AI-powered debugging!  
