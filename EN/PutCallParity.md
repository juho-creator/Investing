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
## Using Bonds

When the strike price of the option exactly matches the face value of the bond and the expiration date is the same:
- Price of XYZ stock (S) = $50
- Strike price of the option (x) = $55
- Present value of x (PV) = $54.46 (bond that will be worth $55 at expiration)
- Price of a 6-month European call option on XYZ stock (C) = $3.00

</br>

1. When put call parity is maintained (P = $7.46)</br>
$3 + $54.46 = P + $50 </br>
$57.46 - $50 = P </br>
$7.46 = P </br>
</br>
</br>


2. When put call parity does not hold (P = $8)</br>
$3 + $54.46 ≠ $8 + $50 </br>
$57.46 ≠ $58 </br>
</br>
</br>

Arbitrage can be pursued as follows:
1. Sell the put option at $8 and buy the call option at $3.  
2. Short sell the underlying stock at $50.
3. This results in an immediate cash inflow of $5 ($8 - $3).

</br>

This results in a guaranteed profit of $0.54 at expiration ($58 - $57.46).</br>
This is because the short stock position offsets the exercise of the put or call options.

Korea Investment & Securities API does not support current market prices for bonds. </br>
It seems that using the real-world investment API to obtain bond prices would suffice for simulation purposes.
</br></br></br></br>

## Using Futures
![image](https://github.com/user-attachments/assets/882a7b6e-6f45-42f1-9399-9aebe1842d53)
</br></br></br>

Arbitrage using futures can be conducted as follows:
1. Identify that put call parity does not hold.
2. Place orders to sell futures, sell puts, and buy calls.
3. Wait until expiration.

- **In-the-Money**: The strike price of the option is advantageous compared to the current price of the underlying asset.
    - Put Option: Current price < Strike price
    - Call Option: Current price > Strike price
</br></br></br>


Assume the strike price of the option and the expiration price of the futures are the same expiration date at $105.
</br>

![image](https://github.com/user-attachments/assets/e63a7a87-57a9-4d7c-b651-852edf2fa3d3)

**Scenario 1**: Futures price < $105  
- Sell 105 Put: In-the-money state, obligation to buy the futures contract at $105 from the put holder  
- Sell Futures: Buy at $105 and sell at $100, resulting in a $5 loss  
- Buy 105 Call: Worthless at expiration, resulting in a $2 premium loss  
Conclusion: The profit from the put option exceeds the losses from the call option and futures, resulting in a net profit of $1.
</br></br>

**Scenario 2**: Futures price > $105  
- Buy 105 Call: In-the-money state, exercise the option to buy the futures contract at $105  
- Sell 105 Put: Worthless at expiration, resulting in a loss  
- Sell Futures: Buy at $105 and sell at $100, resulting in a $5 loss  
Conclusion: The profit from the call option exceeds the losses from the put option and futures, resulting in a net profit of $1.
</br></br>

**Scenario 3**: Futures price = $105  
- Sell 105 Put: Worthless at expiration, no loss  
- Buy 105 Call: Worthless at expiration, resulting in a $2 premium loss  
- Sell Futures: No loss as price matches  
Conclusion: The $6 from option premiums covers the futures expiration loss, resulting in a net profit of $1.
</br></br>

### Code Flow
1. Collect price data
- **Futures**: Current price, expiration date, strike price
- **Call/Put Options**: Current price, expiration date, strike price
</br></br>

2. Verify that strike prices and expiration dates are identical
</br></br>

3. Use the put call parity formula to identify arbitrage opportunities
   
4. Execute trades when arbitrage opportunities are found
</br></br>

# How to determine the expiration date and strike price of all assets?
- Store the list in a CSV file in advance?

| API | Web Socket | 
| -------- | -------- |
| Can scan a vast array of assets for arbitrage | Focus on a single asset for arbitrage |

</br></br>

## References
- [What is Put Call Parity?](https://www.investopedia.com/terms/p/putcallparity.asp)
- [Arbitrage with Put Call Parity Using Futures](https://www.cmegroup.com/education/courses/introduction-to-options/put-call-parity.html)
- [CFA Level (Put Call Parity)](https://www.youtube.com/watch?v=SbkvkU7-dEA&ab_channel=PrepNuggets)


