# -showing-the-code-snippet-for-FIND-BY-AVAILABILITY-test-case
def test_find_product_by_availability(self):
    # Create products with different availability statuses
    available_product = Product(name="AvailableProduct", category="Toys", available=True)
    available_product.save()
    unavailable_product = Product(name="UnavailableProduct", category="Books", available=False)
    unavailable_product.save()
    
    # Retrieve available products
    available_products = Product.find_by_availability(True)
    
    # Assert that only available products are retrieved
    assert all(product.available for product in available_products)
