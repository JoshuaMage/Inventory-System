<script>
    export let img;
    export let productName;
    export let unitOfMeasurement;
    export let description;
    export let brand;
  </script>
  
  <div class="product">
    <img src={img} alt={productName} />
    <h3>{productName}</h3>
    <p>{description}</p>
    <p><strong>Brand:</strong> {brand}</p>
    <p><strong>Unit:</strong> {unitOfMeasurement}</p>
  </div>
  
  <style>
    .product {
      width: 200px;
      padding: 10px;
      margin: 10px;
      border: 1px solid #ccc;
      border-radius: 5px;
      text-align: center;
    }
  
    img {
      width: 100%;
      height: auto;
      border-radius: 5px;
    }
  </style>
  