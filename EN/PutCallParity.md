# Put Call Parity
[![English](https://img.shields.io/badge/lang-English-blue.svg)](https://github.com/juho-creator/Investing/blob/main/EN/PutCallParity.md)
[![한국어](https://img.shields.io/badge/lang-한국어-red.svg)](https://github.com/juho-creator/Investing/blob/main/EN/PutCallParity.md)

</br>

> [!CAUTION]
> **Only applies to European options, where the rights can only be exercised after expiration date**

</br>


Price of a call option implies a specific fair price for the corresponding put option with the **same underlying asset, strike price, and expiration date**, and vice versa. If market prices diverge from this relationship, it signals a mispricing that shrewd traders know to exploit for profit. </br>
- **strike price** : Price at which the option can be bought or sold after expiration date

 </br></br></br>
  
$$ C+PV(x)=P+S $$


- C=Price of the European call option
- PV(x)=Present value of the strike price (x),
discounted from the value on the expiration
date at the risk-free rate
- P=Price of the European put
- S=Spot price or the current market value
of the underlying asset
</br></br></br>



# Put Call Parity Arbitrage
## Using bonds (Unable to execute at mock account)
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
</br></br>


## Using futures
![image](https://github.com/user-attachments/assets/9e1727f2-daa2-4d00-afea-34c506ecc088)


### Code flow
1. Obtain price data
- **futures** : trade price, expiration date, final settlement price
- **Call/put options** : trade price, expiration date, strike price
</br></br>

2. Check if the expiration date and price at expiration are the same
</br></br>

4. Use put call parity formula to determine arbitrage opportunity
   
6. Execute trade when arbitrage opportunity is found
</br></br>


# How would we know the expiration date and strike price of all assets? 
- Save list in csv in advance?
  

| API | Web Socket | 
| -------- | -------- |
| Can skim through vast amount of assets for arbitrage | Can focus on one asset for arbitrage |

</br></br>

## Reference
- [Put Call Parity Arbitrage with futures](https://www.cmegroup.com/education/courses/introduction-to-options/put-call-parity.html)



