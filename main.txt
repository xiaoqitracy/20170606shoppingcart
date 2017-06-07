var Product = require('./Product');
var RandomGenerator = require('./RandomGenerator');
var $ = require('jquery');

var random = new RandomGenerator();

var products = [
    new Product('iPad Pro 9.7', 19900, false),
    new Product('iPad Pro 12.9', 25900, true),
    new Product('iPad', 13900, false)
];

$(function () {
    var $shoppingCart = $('#shoppingCart');
    for (var count = 1; count <= 5; count++) {
        var product = products[random.nextInt(0, products.length)];
        if (product.soldOut) continue;
        var $li = $('<li></li>');
        $li.text(product.name);
        $li.appendTo($shoppingCart);
    }
});