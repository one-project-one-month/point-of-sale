## Point Of Sale (POS)
ဒီ Project က ကုန်ပစ္စည်း ရောင်းဖို့ အတွက် ဖန်တီးထားတဲ့ Idea တစ်ခု ဖြစ်ပါတယ်။
ကျွန်တော်တို့က ဒီ Project အတွက် လိုအပ်တဲ့ Tableလေးတွေ တည်ဆောတ်ထားတယ်။ ကိုယ်လိုအပ်သလို ထပ်ကွန့်ပြီး ချဲ့လို့ရပါတယ်။ ဒီ Project က တစ်လအတွင်း လုပ်ရတာဖြစ်တဲ့အတွက်
အမြန် အသုံးပြုလို့ရမယ့် Table တွေပဲ အရင် ထုတ်ထားပါတယ်။
1. [Product](#product)
2. [Product Category](#product-category)
3. [Shop](#shop)
4. [Staff](#staff)
5. [Sale Invoice](#sale-invoice)
6. [Sale Invoice Detail](#sale-invoice-detail)

## Product
Product Table ကိုကျွန်တော်တို့ကုန်ပစ္စည်းရဲ့ Code, အမည်၊ အမျိုးအစား၊စျေးနှုန်းတွေကိုသိမ်းဖို့တည်ဆောတ်ထားပါတယ်။
```sql
[ProductId] [int] IDENTITY(1,1) NOT NULL
[ProductCode] [nvarchar](50) NOT NULL
[ProductCategoryCode] [nvarchar](50) NOT NULL
[ProductName] [nvarchar](50) NOT NULL
[Price] [decimal](18, 2) NOT NULL
```

## Product Category
Category Table ကို ကျွန်တော်တို့ ကုန်ပစ္စည်းရဲ့အမျိုးအစားတွေကိုသိမ်းဖို့တည်ဆောတ်ထားပါတယ်။
```sql
[ProductCategoryId] [int] IDENTITY(1,1) NOT NULL
[ProductCategoryCode] [varchar](50) NOT NULL
[ProductCategoryName] [varchar](50) NOT NULL
```

## Shop
Shop Table ကို ကျွန်တော်တို့ websiteကိုသုံးတဲ့စျေးဆိုင်တွေရဲ့ Code , အမည် ၊ ဖုန်းနံပါတ် ၊ လိပ်စာအပြည့်အစုံကိုသိမ်းဆည်းရန်တည်ဆောတ်ထားပါတယ်။ကျွန်တော်တို့shopတစ်ခုချင်းစီရဲ့ရောင်းအားကိုကြည်ဖို့အတွတ်လည်းသုံးဖို့စဉ်စားထားပါတယ်။
```sql
[ShopId] [int] IDENTITY(1,1) NOT NULL
[ShopCode] [varchar](50) NOT NULL
[ShopName] [varchar](50) NOT NULL
[MobileNo] [varchar](50) NOT NULL
[Address] [varchar](50) NOT NULL
```

## Staff
Staff Table ကိုကျွန်တော်တို့website ကိုသုံးနေတဲ့ ဝန်ထမ်းတွေရဲ့ code ၊အမည် ၊မွေးနေ့၊လိပ်စာအပြည့်အစုံ၊Gender ၊ ရာထူး ၊ password တွေကိုသိမ်းဖ်ို့အတွတ်တည်ဆောတ်ထားပါတယ်။
```sql
  [StaffId] [int] IDENTITY(1,1) NOT NULL
	[StaffCode] [varchar](50) NOT NULL
	[StaffName] [varchar](50) NOT NULL
	[DateOfBirth] [datetime] NOT NULL
	[MobileNo] [varchar](50) NOT NULL
	[Address] [varchar](50) NOT NULL
	[Gender] [varchar](50) NOT NULL
	[Position] [varchar](50) NOT NULL
	[Password] [varchar](50) NOT NULL
```

## Sale Invoice
SaleInvoice Table ကိုကျွန်တော်တို့ ရောင်းလိုက်လို့ voucher ထုတ်ပေးလိုက်တဲ့အချိန် ၊  vouchers no ၊ စုစုပေါင်းကျသင့်ငွေ ၊ Discount ၊ ရောင်းလိုက်တဲ့staffရဲ့code ၊ အခွန်ပမာဏ ၊ ပေးချေသည့်ပုံစံ ၊ ပေးချေလိုက်တဲ့ပမာဏ ၊ ရရှိတဲ့ပမာဏ ၊ ပြန်အမ်းလိုက်တဲ့ပမာဏ ၊ လာဝယ်တဲ့customer ရဲ့အမည် တို့ကိုသိမ်းထားရန်အတွတ်တည်ဆောတ်ထားပါတယ်။
```sql
[SaleInvoiceId] [int] IDENTITY(1,1) NOT NULL
[SaleInvoiceDateTime] [datetime] NOT NULL
[VoucherNo] [nvarchar](20) NOT NULL
[TotalAmount] [decimal](18, 2) NOT NULL
[Discount] [decimal](18, 2) NOT NULL
[StaffCode] [nvarchar](50) NOT NULL
[Tax] [decimal](18, 2) NOT NULL
[PaymentType] [nvarchar](10) NULL
[CustomerAccountNo] [nvarchar](20) NULL
[PaymentAmount] [decimal](18, 2) NULL
[ReceiveAmount] [decimal](18, 2) NULL
[Change] [decimal](18, 2) NULL
[CustomerCode] [nvarchar](50) NULL
```

## Sale Invoice Detail
SaleInvoiceDetail Table ကိုကျွန်တော်တို့ ရောင်းလိုက်ရတဲ့ကုန်ပစ္စည်းအသေးစိတ်က်ိုသိမ်းချင်လို့တည်ဆောတ်ထားပါတယ်။ သိမ်းထားတဲ့columns တွေကတော့ VoucherNo ၊ ကုန်ပစ္စည်းရဲ့code၊ ရောင်းချလိုက်ရတဲ့ ကုန်ပစ္စည်းအရေအတွတ်၊ စျေးနှုန်း နှင့် ရောင်းချလိုက်တဲ့ပိုက်ဆံပမာဏ တို့ကိုသိမ်းထားပါတယ်။
```sql
[SaleInvoiceDetailId] [int] IDENTITY(1,1) NOT NULL
[VoucherNo] [nvarchar](20) NOT NULL
[ProductCode] [nvarchar](50) NOT NULL
[Quantity] [int] NOT NULL
[Price] [decimal](18, 2) NOT NULL
[Amount] [decimal](18, 2) NOT NULL
```
