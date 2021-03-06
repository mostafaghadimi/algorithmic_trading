<div dir='rtl'>

# بخش اول


## Market Sectors

بخش‌های بازار انواع مختلفی از کالاهای اساسی هستند که قابل معامله هستند.

## Asset Classes

 کلاس دارایی انواع مختلفی از وسایل/ابزارهای واقعی است که برای تبادل‌های مختلف در دسترس است.
 
 دو تا معروف‌ترین‌های آن‌ها `options` و `future` هستند.

  ۱. **future**: قراردادی است که بین خریدار و فروشنده بسته می‌شود و در آن تضمین می‌شود تا یک تاریخ مشخص خریدار، یک مقدار مشخص از کالای تهیه شده توسط خریدار را با قیمت تعیین شده خریداری کند.

۲. **options**: همان future است با این تفاوت که خریدار یا فروشنده می‌توانند قرارداد را لغو کنند. برای این‌که طرفین ضرر زیادی نبینند یک مقدار حداقلی از پول به نام `premium` را در نظر می‌گیرند. (حداقل پولی که برای قرارداد options در نظر گرفته می‌شود.)


![شکل کلی](img/1.png)



## Exchange Order Book

همه‌ی درخواست‌های خرید و فروش کاربر در این قسمت نگهداری می‌شود. اطلاعات آن شامل قیمت، تعداد  سهم، نوع سفارش و اطلاعات خریدار است.


## انواع سفارش

1. IOC (Immediate or Close): 

2. GTD (Good Till Day):

3. Stop orders:

## مدیریت سود و ضرر

به مدیریت سود و ضرر `PnL` یا `Profit and Loss Management` می‌گویند.


۱. به اجرا کردن سفارش خرید، داشتن `long position` می‌گویند. 

۲. به اجرا کردن سفارش فروش، داشتن `short position` می‌گویند.

**نکته:** Long positionها  زمانی  به سود می‌رسند که قیمت بازار بالاتر از قیمت `postion` باشد. یا به عبارت دیگر تابع $f$ مثبت باشد.

<div dir=ltr>

$$ f(x) = market\: price - position\: price$$
</div>

**نکته:** سودهای تحقق نیافته به `long position`هایی می‌گویند که قیمت بازار بالاتر از قیمت postition است اما ما چون سود را نفروخته‌ایم، آن را به عنوان تحقق نیافته در نظر می‌گیریم. (سود بالقوه). در واقع:


<div dir=ltr>

$$ PnL = \Sigma_{s}^{Stocks} (realized\: PnL + unrealized\: PnL) $$
</div>


## Trend Following Strategy


## Mean Reversion Strategy




## Backtesting


Backtesting یک مرحله‌ی مهم برای به دست آوردن آماری است که نشان می‌دهد چقدر استراتژی trading کارآمد است.


# بخش دوم



## Trend Indicator

مطالعه‌ بر روی داده‌های تاریخچه‌ی قیمت‌ها باعث می‌شود که اگر قیمت‌ها برای چند روز ثابت در حال افزایش بودند، یک long position جدید ایجاد کنیم. 


## Momentum Indicator


مطالعه روی قدرت رفتار‌های گذشته است. (درست نفهمیدم)


 ## تفاوت Trend و Momentum





## Support and Resistance Indicator


**Support line:**
وقتی قیمت‌ها در حال کاهش/ریزش هستند، انتظار داریم در نقطه‌ای این ریزش (به‌خاطر تقاضا) متوقف شود که به آن خط حمایت یا support line گفته می‌شود.


**Resistance line:**
 وقتی قیمت‌ها در حال افزایش هستند، ما به دلیل عرضه‌ی کالاها انتظار داریم تا در نقطه‌ای این روند متوقف شود که به آن خط مقاومت یا resistance line می‌گویند.


## روش‌های رایج در تحلیل تکنیکال

1. Simple Moving Average (SMA):

<div dir='ltr'>

$$ SimpleMovingAverage = \frac{\Sigma_{i=1}^{N} P_i}{N} $$

</div>

2. Exponential Moving Average (EMA)

<div dir='ltr'>

$$ EMA = (P - EMA_{old} ) \times \mu + EMA_{old} $$
$$ EMA =  P \times \mu + (1 - \mu) \times EMA_{old} $$
$$ \mu = \frac{2}{n + 1}$$

</div>

3. Absolute Price Oscillator (APO)

<div dir='ltr'>

$$ AbsolutePriceOscillator = EMA_{fast} - EMA_{slow} $$

</div>

4. Moving Average Convergence Divergence (MACD)

<div dir='ltr'>

$$ MACD = EMA_{fast} - EMA_{slow} $$
$$ MACD_{signal} = EMA_{MACD} $$
$$ MACD_{histogram} = MACD - MACD_{signal} $$



</div>

5. Bollinger Bands (BBANDS)

<div dir='ltr'>

$$ BBANDS_{middle} = SMA_{n-periods}$$
$$ BBANDS_{upper} = BBANDS_{middle} + (\beta \times \sigma)$$
$$ BBANDS_{lower} = BBANDS_{middle} - (\beta \times \sigma)$$

$$ \sigma^{2} = \frac{\Sigma_{i=1}^{N}(P_i - SMA) ^ 2}{n} $$
$$ \sigma = \sqrt \sigma ^ 2 $$



</div>

6. Relative Strength Indicator (RSI)

<div dir='ltr'>

$$ if \: price > previous \: price: $$
$$ \rightarrow AbsoluteLossOverPeriod = 0
, AbsoluteGainOverPeriod =  price - previous\: price$$


$$ if \: price < previous \: price: $$
$$ \rightarrow AbsoluteLossOverPeriod = price - previous\: price
, AbsoluteGainOverPeriod =  0$$

$$ RS = \frac{ |\frac{\Sigma GainsOverLastNPeriods}{n}}{\frac{ \Sigma LossesOverLastNPeriods}{n}}$$

$$ RSI = 100 - \frac{100}{1 + RS} $$

</div>

7. Standard Deviation (STDEV)

<div dir='ltr'>

$$ \sigma = \sqrt \frac{\Sigma_{i=1}^{n}(P_i - SMA)^2}{n} $$ 
</div>

8. Momentum (MOM)

<div dir='ltr'>

$$ MOM = Price_t - Price_{t-n}$$ 
</div>

# متفرقه

## return 

<div dir='ltr'>

$$ return = \frac{P_2 - P_1 + dividend}{P_1} $$
</div>


# کلمات مهم

| کلمه | معنی| 
| ------------- |:-------------:|
| promissory notes | سفته |
| bonds | اوراق قرضه |
| supply | عرضه |
| demand | تقاضا |
| profit | سود |
| market | بازار |
| commodity | کالا |
| ephermal |  زود گذر، کم‌دوام | 
| inherent | ذاتی |
| equilibrium‌ |‌ تعادل |
| intuitively |‌ به‌طور شهودی، بصری | 
| retail business | تجارت خرده‌فروشی | 
| asset | دارایی |
| underlying products | کالاهای اساسی | 
| equities | سهام |  
| bid (buy order) | سفارش خرید (پیشنهاد) | 
| ask (sell order) | سفارش فروش | 
| broker | دلال |
| capital | سرمایه | 
| for the sake of | به‌خاطرِِِِِِِ | 
| bankruptcy | ورشکستگی | 
| amend | اصلاح کردن |
| momentum | تکانه | 
| indicator | شاخص، اندیکاتور |
| swing | نوسان داشتن |
| security | اوراق بهادار | 
|‌ exchange | داد و ستد، مبادله | 
| traded | داد و ستد، مبادله |
| fund | صندوق |
| ledger | دفتر کل، جایی که تراکنش‌ها در آن ثبت می‌شوند|
| firm | کارخانه |
| on behalf of | از طرف |
|‌ mutual fund | صندوق سرمایه‌گذاری مشترک | 
| annual | سالانه |
| dividend | سود سهام | 
| shareholder | سهام‌دار | 
| debt | بدهی |
| yield | بازده | 
| OTC (Over The Counter) | فرابورس | 
| intrinsic | ذاتی |
| influx | هجوم |
| liquidity | نقدینگی |
|‌ disclosure | افشاء |‌
| NAV (Net Asset Value) | ارزش خالص دارایی |

## لینک‌های کاربردی
- [توضیح اندیکاتور](https://school.stockcharts.com/doku.php?id=technical_indicators:introduction_to_technical_indicators_and_oscillators#:~:text=An%20oscillator%20is%20an%20indicator,trend%20for%20a%20sustained%20period.)

</div>

