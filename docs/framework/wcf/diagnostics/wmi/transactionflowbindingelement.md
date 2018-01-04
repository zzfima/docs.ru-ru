---
title: TransactionFlowBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0a9656fe-2400-45ca-ad79-92715c8cf190
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0b073efc47ccc1708bf4c58153b1001a21eee25f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="transactionflowbindingelement"></a><span data-ttu-id="da3cc-102">TransactionFlowBindingElement</span><span class="sxs-lookup"><span data-stu-id="da3cc-102">TransactionFlowBindingElement</span></span>
<span data-ttu-id="da3cc-103">TransactionFlowBindingElement</span><span class="sxs-lookup"><span data-stu-id="da3cc-103">TransactionFlowBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da3cc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="da3cc-104">Syntax</span></span>  
  
```  
class TransactionFlowBindingElement : BindingElement  
{  
  string IssuedTokens;  
  string TransactionProtocol;  
  boolean Transactions;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="da3cc-105">Методы</span><span class="sxs-lookup"><span data-stu-id="da3cc-105">Methods</span></span>  
 <span data-ttu-id="da3cc-106">Класс TransactionFlowBindingElement не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="da3cc-106">The TransactionFlowBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="da3cc-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="da3cc-107">Properties</span></span>  
 <span data-ttu-id="da3cc-108">Класс TransactionFlowBindingElement имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="da3cc-108">The TransactionFlowBindingElement class has the following properties:</span></span>  
  
### <a name="issuedtokens"></a><span data-ttu-id="da3cc-109">IssuedTokens</span><span class="sxs-lookup"><span data-stu-id="da3cc-109">IssuedTokens</span></span>  
 <span data-ttu-id="da3cc-110">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="da3cc-110">Data type: string</span></span>  
  
 <span data-ttu-id="da3cc-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="da3cc-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="da3cc-112">Задает требование для заголовка выданных маркеров безопасности (IssuedTokens из WS-Trust).</span><span class="sxs-lookup"><span data-stu-id="da3cc-112">Specifies the requirement for an issued security tokens header (IssuedTokens from WS-Trust).</span></span>  
  
### <a name="transactionprotocol"></a><span data-ttu-id="da3cc-113">TransactionProtocol</span><span class="sxs-lookup"><span data-stu-id="da3cc-113">TransactionProtocol</span></span>  
 <span data-ttu-id="da3cc-114">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="da3cc-114">Data type: string</span></span>  
  
 <span data-ttu-id="da3cc-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="da3cc-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="da3cc-116">Протокол транзакций, используемый службой для передачи транзакций.</span><span class="sxs-lookup"><span data-stu-id="da3cc-116">The transactions protocol used by the service to flow transactions.</span></span>  
  
### <a name="transactions"></a><span data-ttu-id="da3cc-117">Транзакции</span><span class="sxs-lookup"><span data-stu-id="da3cc-117">Transactions</span></span>  
 <span data-ttu-id="da3cc-118">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="da3cc-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="da3cc-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="da3cc-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="da3cc-120">Указывает, поддерживается ли входящая транзакция.</span><span class="sxs-lookup"><span data-stu-id="da3cc-120">Indicates whether the incoming transaction is supported.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da3cc-121">Требования</span><span class="sxs-lookup"><span data-stu-id="da3cc-121">Requirements</span></span>  
  
|<span data-ttu-id="da3cc-122">MOF</span><span class="sxs-lookup"><span data-stu-id="da3cc-122">MOF</span></span>|<span data-ttu-id="da3cc-123">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="da3cc-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="da3cc-124">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="da3cc-124">Namespace</span></span>|<span data-ttu-id="da3cc-125">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="da3cc-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="da3cc-126">См. также</span><span class="sxs-lookup"><span data-stu-id="da3cc-126">See Also</span></span>  
 <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>
