React has some built-in type checking capabilities. For example, if you want to check the types of props your component receives, you can assign the special propTypes property;

import PropTypes from 'prop-types';

class Header extends React.Component {
	render() {
		return (
			<h1>Hello, {this.props.name} </h1>
		);
	}
}

Header.propTypes = {
  name: PropTypes.string
};

This is an example of using propTypes on a class component, and propTypes can used on a functional component as well:

const Header = (props) => <h1>Hello, {props.name} </h1>;

Header.propTypes = {
	name: PropTypes.string
};

Here is a list of propType validators:

PropTypes.any: The prop can be of any data type
PropTypes.bool: The prop should be a Boolean
PropTypes.number: The prop should be a number
PropTypes.string: The prop should be a string
PropTypes.func: The prop should be a function
PropTypes.array: The prop should be an array
PropTypes.object: The prop should be an object
PropTypes.symbol: The prop should be a symbol
