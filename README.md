<div align="center">

  <img src="./public/images/shared/logo.svg" alt="logo" width="40" height="auto">

  <h2>Space Tourism</h2>

  <h3>
    <a href="https://space-tourism-multi-page-website-ivory.vercel.app/">
      <strong>View Demo</strong>
    </a>
    ||
    <a href="https://www.frontendmentor.io/solutions/space-tourism-multipage-website-HxYs_fHRjN">
      <strong>Frontend Mentor</strong>
    </a>
  </h3>

  <div align="center">
    <a href="https://github.com/aniru-dh21/Space-Tourism-Multi-Page-Website/issues">Report Bug</a>
    •
    <a href="https://github.com/aniru-dh21/Space-Tourism-Multi-Page-Website/pulls">Request Features</a>
  </div>

  <hr>
  
</div>

<div align="center">

  <img src="https://img.shields.io/badge/Status-Completed-success?style=flat" alt="Status" />

  <a href="https://twitter.com/Dh21Aniru" target="_blank">
    <img alt='Twitter' src="https://img.shields.io/badge/@Dh21Aniru-100000?style=for-the-badge&logo=Twitter&logoColor=00C9F7&labelColor=3F3F3F&color=0092FA">
  </a>

  <a href="https://www.linkedin.com/in/ramachandra-anirudh-vemulapalli-554b551ba/" target="_blank">
    <img src="https://img.shields.io/badge/@Dh21Aniru-100000?style=for-the-badge&logo=LinkedIn&logoColor=00a0dc&labelColor=2F2F2F&color=0077b5">
  </a>
  
</div>

<p align="center">
  A multi-page space tourism website - discover destinations, meet the crew, and delve into technology. 
</p>

<a align="center" href="https://space-tourism-multi-page-website-ivory.vercel.app/">

  ![Screenshot](./public/thumbnail-preview.jpg)
  
</a>

## Table of Contents

- [Key Features](#key-features)
- [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I Learned](#what-i-learned)
- [Installation](#installation)
- [Author](#author)

## Key Features

Users should be able to:

- Viw each page and be able to toggle between the tabs to see new information
- View the optimal layout for each for each of the website's page depending on their device's screen size
- See hover states for all interactive elements on the page

## Links

- View Demo - [Live](https://space-tourism-multi-page-website-ivory.vercel.app/)
- Solution Page - [Frontend Mentor Solution](https://www.frontendmentor.io/solutions/space-tourism-multipage-website-HxYs_fHRjN)

## My Process

### Tech Stack

- React
- React router
- Styled components
- Vite

### What I Learned

During the development of the Space Tourism Website, I encountered several challenges and gained valuable insights into various aspects of web development.

#### Dynamic Backgrounds with React Router and Styled Components

One of the challenges faced was dynamically changing the background image based on the page the user navigates to. Wanting to provide a visually appealing experience by adjusting the background according to each page.

```css
const StyledAppLayout = styled.div.withConfig({
  shouldForwardProp: (prop) => "pageLocation" !== prop,
})`
  background-image: ${(props) =>
    `url("/images/${props.pageLocation}/background-${props.pageLocation}-mobile.jpg")`};

  @media screen and (min-width: 768px) {
    background-image: ${(props) =>
      `url("/images/${props.pageLocation}/background-${props.pageLocation}-tablet.jpg")`};
  }

  @media screen and (min-width: 1024px) {
    background-image: ${(props) =>
      `url("/images/${props.pageLocation}/background-${props.pageLocation}-desktop.jpg")`};
  }

  // Additional styles...
`;
```

Utilizing React Router's `useLocation` hook to get the current location, extrated the page name, and passed it as a prop to styled component. Leveraging `styled-components` allowing to dynamically set baackground images based on the page, creating a seamless transition between pages.

#### React Router and Conditional Redirects

Implementing conditional redirects with React Router was crucial for ensuring a smooth user experience. For instance, when a user lands on the `/crew` route without specifying a particular crew member. To address this, implemented conditional redirects using React Router. 

```jsx
function CrewContents() {
  const crews = jsonData.crew;
  const { name: crewName } = useParams();
  const activeName = crewName || crews[0].name;
  const currentCrew = crews.find((crew) => crew.name === activeName);

  // Redirect to the first crew member if no specific crew is selected
  if (!crewName) {
    return <Navigate to={`/crew/${crews[0].name}`} replace />;
  }

  // Redirect to a 404 page if the specified crew member is not found
  if (!currentCrew) {
    return <NotFound />;
  }

  // Rest of the component rendering
  return (
    // ...
  );
}
```

In this code snippet, It first check if `crewName` is not provided, and if so, it redirect the user to the first crew member's page. Additionally, if the specified crew member is not found in the dataset, a redirect to a custom NotFound page is implemented.

This approach ensures a seamless user experience, providing default navigation when needed and gracefully handling scenarios where a crew member is not found.

## Installation

- Clone this repo:

```sh
git clone https://github.com/aniru-dh21/Space-Tourism-Multi-Page-Website.git
```

- Install Dependencies:

```sh
npm install
```

- Build Command:

```sh
npm run build
```

- Live Server:

```sh
npm run dev
```

## Author

<b>Ramachandra Anirudh Vemulapalli</b>

- Twitter - [@Dh21Aniru](https://twitter.com/Dh21Aniru)
- LinkedIn - [@Ramachandra-Anirudh-Vemulapalli](https://www.linkedin.com/in/ramachandra-anirudh-vemulapalli-554b551ba/)
- Frontend Mentor - [@aniru-dh21](https://www.frontendmentor.io/profile/aniru-dh21)
- Github - [@aniru-dh21](https://github.com/aniru-dh21)
