The actual implementation of useState and useEffect hooks in React are very advanced. However, we can use them to abstract reusable state logic.

import { useState, useEffect } from "react";
 
const useStyles = (stylesSM, stylesLG) => {
 const [width, setWidth] = useState(document.documentElement.clientWidth);
 
 window.addEventListener("resize", () => {
   setWidth(document.documentElement.clientWidth);
 });
 
 if (width < 992) {
   return stylesSM;
 }
 
 return stylesLG;
};
 
export default useStyles;

To fix the memory leak:
import { useState, useEffect } from "react";
 
const useStyles = (stylesSM, stylesLG) => {
 const [width, setWidth] = useState(document.documentElement.clientWidth);
 
 function updateWidth() {
   setWidth(document.documentElement.clientWidth);
 }
 
 useEffect(() => {
   window.addEventListener("resize", updateWidth);
 
   return function () {
     window.removeEventListener(updateWidth);
   };
 }, []);
 
 if (width < 992) {
   return stylesSM;
 }
 
 return stylesLG;
};
 
export default useStyles;
