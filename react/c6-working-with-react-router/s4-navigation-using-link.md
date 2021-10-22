
	You might have noticed that right now, the only way to go to another page is by typing the URL. If you want a navigable interface, something like a sidebar or a top or bottom navbar, you can use the Link component to create links to certain routes. Here’s an example - 

function Navbar() {
  return (
    <div>
      <Link to="/">Home </Link>
      <Link to="/about">About Us </Link>
      <Link to="/shop">Shop Now </Link>
    </div>
  );
};

