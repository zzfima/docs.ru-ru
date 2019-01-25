---
title: TransactionFlowBindingElement
ms.date: 03/30/2017
ms.assetid: 0a9656fe-2400-45ca-ad79-92715c8cf190
ms.openlocfilehash: d0311837ebb8112d9492fb548492bcd3e10230e7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54514577"
---
# <a name="transactionflowbindingelement"></a><span data-ttu-id="b5490-102">TransactionFlowBindingElement</span><span class="sxs-lookup"><span data-stu-id="b5490-102">TransactionFlowBindingElement</span></span>
<span data-ttu-id="b5490-103">TransactionFlowBindingElement</span><span class="sxs-lookup"><span data-stu-id="b5490-103">TransactionFlowBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5490-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b5490-104">Syntax</span></span>  
  
```csharp
class TransactionFlowBindingElement : BindingElement  
{  
  string IssuedTokens;  
  string TransactionProtocol;  
  boolean Transactions;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="b5490-105">Методы</span><span class="sxs-lookup"><span data-stu-id="b5490-105">Methods</span></span>  
 <span data-ttu-id="b5490-106">Класс TransactionFlowBindingElement не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="b5490-106">The TransactionFlowBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="b5490-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="b5490-107">Properties</span></span>  
 <span data-ttu-id="b5490-108">Класс TransactionFlowBindingElement имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="b5490-108">The TransactionFlowBindingElement class has the following properties:</span></span>  
  
### <a name="issuedtokens"></a><span data-ttu-id="b5490-109">IssuedTokens</span><span class="sxs-lookup"><span data-stu-id="b5490-109">IssuedTokens</span></span>  
 <span data-ttu-id="b5490-110">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="b5490-110">Data type: string</span></span>  
  
 <span data-ttu-id="b5490-111">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="b5490-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b5490-112">Задает требование для заголовка выданных маркеров безопасности (IssuedTokens из WS-Trust).</span><span class="sxs-lookup"><span data-stu-id="b5490-112">Specifies the requirement for an issued security tokens header (IssuedTokens from WS-Trust).</span></span>  
  
### <a name="transactionprotocol"></a><span data-ttu-id="b5490-113">TransactionProtocol</span><span class="sxs-lookup"><span data-stu-id="b5490-113">TransactionProtocol</span></span>  
 <span data-ttu-id="b5490-114">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="b5490-114">Data type: string</span></span>  
  
 <span data-ttu-id="b5490-115">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="b5490-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b5490-116">Протокол транзакций, используемый службой для передачи транзакций.</span><span class="sxs-lookup"><span data-stu-id="b5490-116">The transactions protocol used by the service to flow transactions.</span></span>  
  
### <a name="transactions"></a><span data-ttu-id="b5490-117">Транзакции</span><span class="sxs-lookup"><span data-stu-id="b5490-117">Transactions</span></span>  
 <span data-ttu-id="b5490-118">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="b5490-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="b5490-119">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="b5490-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b5490-120">Указывает, поддерживается ли входящая транзакция.</span><span class="sxs-lookup"><span data-stu-id="b5490-120">Indicates whether the incoming transaction is supported.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b5490-121">Требования</span><span class="sxs-lookup"><span data-stu-id="b5490-121">Requirements</span></span>  
  
|<span data-ttu-id="b5490-122">MOF</span><span class="sxs-lookup"><span data-stu-id="b5490-122">MOF</span></span>|<span data-ttu-id="b5490-123">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="b5490-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="b5490-124">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="b5490-124">Namespace</span></span>|<span data-ttu-id="b5490-125">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="b5490-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b5490-126">См. также</span><span class="sxs-lookup"><span data-stu-id="b5490-126">See also</span></span>
- <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>
