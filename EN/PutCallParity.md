# Put Call Parity
Price of a call option implies a specific fair price for the corresponding put option with the **same underlying asset, strike price, and expiration date**, and vice versa. If market prices diverge from this relationship, it signals a mispricing that shrewd traders know to exploit for profit.

* Only applies to European options, where the rights can only be exercised after expiration date. </br></br></br>
  
$$ C+PV(x)=P+S $$


- C=Price of the European call option
- PV(x)=Present value of the strike price (x),
discounted from the value on the expiration
date at the risk-free rate
- P=Price of the European put
- S=Spot price or the current market value
of the underlying asset
</br></br></br>

# What exactly is the strike price? 
Price at which the option can be bought or sold after expiration date
​</br></br></br>


# Example of Put Call Parity Arbitrage 
- Price of XYZ stock (S) = $50
- Strike price of the options (x) = $55
- Present value (PV) of x = $54.46
- Price of a six-month European call option (C) on XYZ stock = $3.00

</br></br>
$3 + $54.46 = P + $50 </br>
$57.46 - $50 = P </br>
$7.46 = P </br>
</br>
</br>




Call < Put </br>

$3 + $54.46 ≠ $8 + $50 </br>

$57.46 ≠ $58 </br>
</br>
</br>



Put > Call </br>


1. selling the put option for $8, buying the call option for $3,  
2. shorting the underlying stock at $50. 
3. immediate cash inflow of $5 ($8 - $3).
</br>

At expiration, the arbitrageur would have a guaranteed profit of $0.54 ($57.46 - $57) 
because the short stock position would cancel out the exercise of either the put or call option.
