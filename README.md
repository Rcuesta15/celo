# celo
// SPDX-License-Identifier: MIT  

pragma solidity >=0.7.0 <0.9.0;
contract Marketplace {  

    string public product = "Burger";  
}
contract Marketplace {

    string internal product;

    function writeProduct(string memory _product) public {
        product = _product;
    }
}contract Marketplace {

    string internal product;

    function writeProduct(string memory _product) public {
        product = _product;
    }

    function readProduct() public view returns (string memory) {
        return product;
    }

}}contract Marketplace {

    mapping (uint => string) internal products;
    function writeProduct(uint _index, string memory _product) public {
	products[_index] = _product;
}
function readProduct(uint _index) public view returns (string memory) {
	return products[_index];
}
contract Marketplace {

    struct Product {
        address payable owner;
        string name;
        string image;
        string description;
        string location;
        uint price;
        uint sold;
    }
    mapping (uint => Product) internal products;
    function writeProduct(
		uint _index, 
		string memory _name,
		string memory _image,
		string memory _description, 
		string memory _location, 
		uint _price
	) public {
		uint _sold = 0;
		products[_index] = Product(
			payable(msg.sender),
			_name,
			_image,
			_description,
			_location,
			_price,
			_sold
		);
	}
  function readProduct(uint _index) public view returns (
		address payable,
		string memory, 
		string memory, 
		string memory, 
		string memory, 
		uint, 
		uint
	) {
		return (
			products[_index].owner, 
			products[_index].name, 
			products[_index].image, 
			products[_index].description, 
			products[_index].location, 
			products[_index].price,
			products[_index].sold
		);
	}
