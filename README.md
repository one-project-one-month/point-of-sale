## Point Of Sale (POS)
> ဒီ Project က ကုန်ပစ္စည်း ရောင်းဖို့ အတွက် ဖန်တီးထားတဲ့ Idea တစ်ခု ဖြစ်ပါတယ်။

Frontend
- [Flutter](https://github.com/sannlynnhtun-coding/pos_frontend_flutter)
- [Next.js](https://github.com/sannlynnhtun-coding/pos_frontend_next)
- [React.js with TypeScript](https://github.com/sannlynnhtun-coding/pos_frontend_react_ts)
- [React.js](https://github.com/sannlynnhtun-coding/pos_frontend_react)
- [Vue.js](https://github.com/sannlynnhtun-coding/pos_frontend_vue)

Backend
- [Laravel](https://github.com/sannlynnhtun-coding/pos_backend_laravel)
- [Next.js](https://github.com/sannlynnhtun-coding/pos_frontend_next)
- [C#](https://github.com/sannlynnhtun-coding/pos_backend_csharp)

ကျွန်တော်တို့က ဒီ Project အတွက် လိုအပ်တဲ့ Tableလေးတွေ တည်ဆောက်ထားတယ်။ ကိုယ်လိုအပ်သလို ထပ်ကွန့်ပြီး ချဲ့လို့ရပါတယ်။ ဒီ Project က တစ်လအတွင်း လုပ်ရတာဖြစ်တဲ့အတွက်
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

## Store Procedure for Dashboard
```sql

/****** Object:  StoredProcedure [dbo].[sp_Dashboard]    Script Date: 5/24/2024 9:42:18 PM ******/
DROP PROCEDURE [dbo].[sp_Dashboard]
GO

/****** Object:  StoredProcedure [dbo].[sp_Dashboard]    Script Date: 5/24/2024 9:42:18 PM ******/
SET ANSI_NULLS ON
GO

SET QUOTED_IDENTIFIER ON
GO

---------------------------------------------------------------------------------------------------------------
-- Test Script
---------------------------------------------------------------------------------------------------------------
/*
DECLARE @SaleInvoiceDate		 DATETIME		SET @SaleInvoiceDate =GETDATE()

EXEC sp_Dashboard				@SaleInvoiceDate
*/
---------------------------------------------------------------------------------------------------------------
-- Change History
---------------------------------------------------------------------------------------------------------------
-- 22/May/2024	HEIN - Create New Sp
---------------------------------------------------------------------------------------------------------------

CREATE PROCEDURE [dbo].[sp_Dashboard] 
( 
	@SaleInvoiceDate   DATETIME
)
AS
BEGIN 
	---------------------------------------------------------------------------------------------------------------	
	-- Prepare a temp table for dashboard
	---------------------------------------------------------------------------------------------------------------
	CREATE TABLE #WeeklySalesReport (
		SaleInvoiceDate DATETIME,
		Quantity INT,
		Amount DECIMAL(18, 2)
	);

	CREATE TABLE #DailySalesReport (
		SaleInvoiceDate DATETIME,
		ProductName NVARCHAR(50),
		Quantity INT,
		Amount DECIMAL(18, 2)
	);

	CREATE TABLE #MonthlySalesReport (
		SaleInvoiceDate DATETIME,
		Amount DECIMAL(18, 2)
	);

	CREATE TABLE #YearlySalesReport (
		YEAR INT,
		Amount DECIMAL(18, 2)
	);
	
	IF(ISNULL(@SaleInvoiceDate,'') = '') BEGIN
	  SET @SaleInvoiceDate = GETDATE()
	END
	------------------------------------------------------------------------------------------------------------------
	-- Retrieve the Dataset #2 (DailySalesReport)
    	------------------------------------------------------------------------------------------------------------------
	INSERT INTO #DailySalesReport(SaleInvoiceDate, Quantity, Amount)
	SELECT CONVERT(DATE,SI.SaleInvoiceDateTime) AS SaleInvoiceDate, ISNULL(SID.Quantity,0), ISNULL(SID.Amount,0) from Tbl_SaleInvoice (NOLOCK) AS SI 
											INNER JOIN Tbl_SaleInvoiceDetail (NOLOCK) AS SID ON SID.VoucherNo = SI.VoucherNo 
											WHERE CONVERT(DATE,SaleInvoiceDateTime) = CONVERT(DATE,@SaleInvoiceDate)
	---------------------------------------------------------------------------------------------------------------	
	-- Retrieve the Dataset #3 (WeeklySalesReport)
	---------------------------------------------------------------------------------------------------------------

	INSERT INTO #WeeklySalesReport(SaleInvoiceDate, Quantity, Amount)
	SELECT CONVERT(DATE,SI.SaleInvoiceDateTime) AS SaleInvoiceDate, SUM(ISNULL(SID.Quantity,0)), SUM(ISNULL(SID.Amount,0)) from Tbl_SaleInvoice AS SI 
											INNER JOIN Tbl_SaleInvoiceDetail AS SID ON SID.VoucherNo = SI.VoucherNo 
											WHERE CONVERT(DATE,SaleInvoiceDateTime) BETWEEN CONVERT(DATE,DATEADD(day, -7, @SaleInvoiceDate))
											AND CONVERT(DATE,@SaleInvoiceDate) GROUP BY SI.SaleInvoiceDateTime

	---------------------------------------------------------------------------------------------------------------	
	-- Retrieve the Dataset #4 (MonthlySalesReport)
	---------------------------------------------------------------------------------------------------------------
	DECLARE @StartDate DATE SET @StartDate = DATEADD(MONTH, DATEDIFF(MONTH, 0, @SaleInvoiceDate), 0)
	DECLARE @EndDate DATE SET @EndDate = DATEADD(SECOND, -1, DATEADD(MONTH, 1, DATEADD(MONTH, DATEDIFF(MONTH, 0, @SaleInvoiceDate), 0)))

	INSERT INTO #MonthlySalesReport(SaleInvoiceDate, Amount)
	SELECT CONVERT(DATE,SI.SaleInvoiceDateTime) AS SaleInvoiceDate, SUM(ISNULL(SID.Amount,0)) from Tbl_SaleInvoice (NOLOCK) AS SI 
											INNER JOIN Tbl_SaleInvoiceDetail (NOLOCK) AS SID ON SID.VoucherNo = SI.VoucherNo 
											WHERE CONVERT(DATE,SaleInvoiceDateTime) BETWEEN CONVERT(DATE,@StartDate) AND CONVERT(DATE,@EndDate)
											GROUP BY CONVERT(DATE,SaleInvoiceDateTime)
	---------------------------------------------------------------------------------------------------------------	
	-- Retrieve the Dataset #5 (YearlySalesReport)
	---------------------------------------------------------------------------------------------------------------

	INSERT INTO #YearlySalesReport(YEAR, Amount)
	SELECT YEAR(SaleInvoiceDateTime), SUM(ISNULL(SID.Amount,0)) from Tbl_SaleInvoice (NOLOCK) AS SI 
											INNER JOIN Tbl_SaleInvoiceDetail (NOLOCK) AS SID ON SID.VoucherNo = SI.VoucherNo 
											WHERE YEAR(SaleInvoiceDateTime) = YEAR(@SaleInvoiceDate) GROUP BY YEAR(SaleInvoiceDateTime)
	------------------------------------------------------------------------------------------------------------------
	-- Return DataSet
	------------------------------------------------------------------------------------------------------------------
	------------------------------------------------------------------------------------------------------------------
	-- Retrieve  Dataset #1  (the best seller top ten Product)
    	------------------------------------------------------------------------------------------------------------------
	SELECT TOP 10 P.ProductName, SUM(ISNULL(SD.Quantity,0)) AS TotalQty FROM Tbl_SaleInvoiceDetail AS SD INNER JOIN Tbl_Product AS P ON P.ProductCode = SD.ProductCode  GROUP BY SD.ProductCode,P.ProductName 	ORDER BY SUM(SD.Quantity) DESC
	------------------------------------------------------------------------------------------------------------------
	-- Retrieve  Dataset #2  (DailySalesReport)
   	------------------------------------------------------------------------------------------------------------------
	SELECT SaleInvoiceDate,Amount FROM #DailySalesReport ORDER BY SaleInvoiceDate
	------------------------------------------------------------------------------------------------------------------
	-- Retrieve  Dataset #3  (WeeklySalesReport)
    	------------------------------------------------------------------------------------------------------------------
	SELECT SaleInvoiceDate,Amount FROM #WeeklySalesReport ORDER BY SaleInvoiceDate
	------------------------------------------------------------------------------------------------------------------
	-- Retrieve  Dataset #4  (MonthlySalesReport)
    	------------------------------------------------------------------------------------------------------------------
	SELECT SaleInvoiceDate,Amount FROM #MonthlySalesReport ORDER BY SaleInvoiceDate
	------------------------------------------------------------------------------------------------------------------
	-- Retrieve  Dataset #5  (YearlySalesReport)
    	------------------------------------------------------------------------------------------------------------------
	SELECT YEAR,Amount FROM #YearlySalesReport
	-------------------------------------------
	-- Remove Temp table
	-------------------------------------------
	DROP TABLE #DailySalesReport
	DROP TABLE #WeeklySalesReport
	DROP TABLE #MonthlySalesReport
	DROP TABLE #YearlySalesReport
END
GO
```
