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
ms.openlocfilehash: fa5394e874e35b80b01796642e18d69c71e867dc
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="transactionflowbindingelement"></a><span data-ttu-id="b1378-102">TransactionFlowBindingElement</span><span class="sxs-lookup"><span data-stu-id="b1378-102">TransactionFlowBindingElement</span></span>
<span data-ttu-id="b1378-103">TransactionFlowBindingElement</span><span class="sxs-lookup"><span data-stu-id="b1378-103">TransactionFlowBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1378-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b1378-104">Syntax</span></span>  
  
```  
class TransactionFlowBindingElement : BindingElement  
{  
  string IssuedTokens;  
  string TransactionProtocol;  
  boolean Transactions;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="b1378-105">Методы</span><span class="sxs-lookup"><span data-stu-id="b1378-105">Methods</span></span>  
 <span data-ttu-id="b1378-106">Класс TransactionFlowBindingElement не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="b1378-106">The TransactionFlowBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="b1378-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="b1378-107">Properties</span></span>  
 <span data-ttu-id="b1378-108">Класс TransactionFlowBindingElement имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="b1378-108">The TransactionFlowBindingElement class has the following properties:</span></span>  
  
### <a name="issuedtokens"></a><span data-ttu-id="b1378-109">IssuedTokens</span><span class="sxs-lookup"><span data-stu-id="b1378-109">IssuedTokens</span></span>  
 <span data-ttu-id="b1378-110">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="b1378-110">Data type: string</span></span>  
  
 <span data-ttu-id="b1378-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="b1378-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b1378-112">Задает требование для заголовка выданных маркеров безопасности (IssuedTokens из WS-Trust).</span><span class="sxs-lookup"><span data-stu-id="b1378-112">Specifies the requirement for an issued security tokens header (IssuedTokens from WS-Trust).</span></span>  
  
### <a name="transactionprotocol"></a><span data-ttu-id="b1378-113">TransactionProtocol</span><span class="sxs-lookup"><span data-stu-id="b1378-113">TransactionProtocol</span></span>  
 <span data-ttu-id="b1378-114">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="b1378-114">Data type: string</span></span>  
  
 <span data-ttu-id="b1378-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="b1378-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b1378-116">Протокол транзакций, используемый службой для передачи транзакций.</span><span class="sxs-lookup"><span data-stu-id="b1378-116">The transactions protocol used by the service to flow transactions.</span></span>  
  
### <a name="transactions"></a><span data-ttu-id="b1378-117">Транзакции</span><span class="sxs-lookup"><span data-stu-id="b1378-117">Transactions</span></span>  
 <span data-ttu-id="b1378-118">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="b1378-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="b1378-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="b1378-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b1378-120">Указывает, поддерживается ли входящая транзакция.</span><span class="sxs-lookup"><span data-stu-id="b1378-120">Indicates whether the incoming transaction is supported.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b1378-121">Требования</span><span class="sxs-lookup"><span data-stu-id="b1378-121">Requirements</span></span>  
  
|<span data-ttu-id="b1378-122">MOF</span><span class="sxs-lookup"><span data-stu-id="b1378-122">MOF</span></span>|<span data-ttu-id="b1378-123">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="b1378-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="b1378-124">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="b1378-124">Namespace</span></span>|<span data-ttu-id="b1378-125">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="b1378-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b1378-126">См. также</span><span class="sxs-lookup"><span data-stu-id="b1378-126">See Also</span></span>  
 <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>
