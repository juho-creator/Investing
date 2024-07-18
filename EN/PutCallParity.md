# Put Call Parity
[![English](https://img.shields.io/badge/lang-English-blue.svg)](https://github.com/juho-creator/Investing/blob/main/EN/PutCallParity.md)
[![한국어](https://img.shields.io/badge/lang-한국어-red.svg)](https://github.com/juho-creator/Investing/blob/main/KR/PutCallParity.md)

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
</br></br></br></br>



## Using futures
![image](https://github.com/user-attachments/assets/9e1727f2-daa2-4d00-afea-34c506ecc088)

Let the strike price of the options and the expiration price of futures be $105 with the same expiration date. </br>

**Scenario 1** : Futures price < $105 </br>
If futures price is less than the strike price, 
- Short 105 PUT : Profitable when exercised above the strike price.
- Long 105 CALL : We don't want to sell lower from where we bought so we'll let it expire and option premium amount is lost.
- Short Futures : Short futures expire, and expiration price of loss occurs

The profit from put option outweighs the call option and futures, resulting in net profit.
   
</br></br>


**Scenario 2** : Futures price > $105  </br>

If futures price is greater than the strike price
- Long 105 CALL : 
- Short 105 PUT : 
- Short Futures : (Expiration)

The profit from put option outweighs the call option and futures, resulting in net profit.
   
</br></br>


**Scenario 3** : Futures price = $105  </br>
If futures price is equivalent than the strike price, the $6 gained from option premium covers up the loss from short futures expiring.
- Short 105 PUT (Profitable)
- Long 105 CALL (Loss)
- Short Futures (Expiration)

</br></br>

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
- [CFA level (Put Call parity)](https://www.youtube.com/watch?v=SbkvkU7-dEA&ab_channel=PrepNuggets)



