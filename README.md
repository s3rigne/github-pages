import PropTypes from "prop-types";

function Checkout({ product, onBack, onPay }) {
  return (
    <section id="checkout">
      <h2>Checkout</h2>
      <p>Product: {product.name}</p>
      <p>Total: ${product.price}</p>
      <select id="payment-method">
        <option value="wave">Wave</option>
        <option value="orange-money">Orange Money</option>
      </select>
      <button onClick={() => onPay(document.getElementById("payment-method").value)}>Pay Now</button>
      <p id="payment-status"></p>
      <button onClick={onBack}>Back to Products</button>
    </section>
  );
}

Checkout.propTypes = {
  product: PropTypes.shape({
    name: PropTypes.string.isRequired,
    price: PropTypes.number.isRequired,
  }).isRequired,
  onBack: PropTypes.func.isRequired,
  onPay: PropTypes.func.isRequired,
};

export default Checkout;