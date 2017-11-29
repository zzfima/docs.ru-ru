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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4c65eb1689d1411cb9083967b9a29c946b7568b7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="transactionflowbindingelement"></a><span data-ttu-id="bc9d5-102">TransactionFlowBindingElement</span><span class="sxs-lookup"><span data-stu-id="bc9d5-102">TransactionFlowBindingElement</span></span>
<span data-ttu-id="bc9d5-103">TransactionFlowBindingElement</span><span class="sxs-lookup"><span data-stu-id="bc9d5-103">TransactionFlowBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc9d5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bc9d5-104">Syntax</span></span>  
  
```  
class TransactionFlowBindingElement : BindingElement  
{  
  string IssuedTokens;  
  string TransactionProtocol;  
  boolean Transactions;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="bc9d5-105">Методы</span><span class="sxs-lookup"><span data-stu-id="bc9d5-105">Methods</span></span>  
 <span data-ttu-id="bc9d5-106">Класс TransactionFlowBindingElement не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="bc9d5-106">The TransactionFlowBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="bc9d5-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="bc9d5-107">Properties</span></span>  
 <span data-ttu-id="bc9d5-108">Класс TransactionFlowBindingElement имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="bc9d5-108">The TransactionFlowBindingElement class has the following properties:</span></span>  
  
### <a name="issuedtokens"></a><span data-ttu-id="bc9d5-109">IssuedTokens</span><span class="sxs-lookup"><span data-stu-id="bc9d5-109">IssuedTokens</span></span>  
 <span data-ttu-id="bc9d5-110">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="bc9d5-110">Data type: string</span></span>  
  
 <span data-ttu-id="bc9d5-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="bc9d5-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bc9d5-112">Задает требование для заголовка выданных маркеров безопасности (IssuedTokens из WS-Trust).</span><span class="sxs-lookup"><span data-stu-id="bc9d5-112">Specifies the requirement for an issued security tokens header (IssuedTokens from WS-Trust).</span></span>  
  
### <a name="transactionprotocol"></a><span data-ttu-id="bc9d5-113">TransactionProtocol</span><span class="sxs-lookup"><span data-stu-id="bc9d5-113">TransactionProtocol</span></span>  
 <span data-ttu-id="bc9d5-114">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="bc9d5-114">Data type: string</span></span>  
  
 <span data-ttu-id="bc9d5-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="bc9d5-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bc9d5-116">Протокол транзакций, используемый службой для передачи транзакций.</span><span class="sxs-lookup"><span data-stu-id="bc9d5-116">The transactions protocol used by the service to flow transactions.</span></span>  
  
### <a name="transactions"></a><span data-ttu-id="bc9d5-117">Транзакции</span><span class="sxs-lookup"><span data-stu-id="bc9d5-117">Transactions</span></span>  
 <span data-ttu-id="bc9d5-118">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="bc9d5-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="bc9d5-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="bc9d5-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bc9d5-120">Указывает, поддерживается ли входящая транзакция.</span><span class="sxs-lookup"><span data-stu-id="bc9d5-120">Indicates whether the incoming transaction is supported.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc9d5-121">Требования</span><span class="sxs-lookup"><span data-stu-id="bc9d5-121">Requirements</span></span>  
  
|<span data-ttu-id="bc9d5-122">MOF</span><span class="sxs-lookup"><span data-stu-id="bc9d5-122">MOF</span></span>|<span data-ttu-id="bc9d5-123">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="bc9d5-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="bc9d5-124">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="bc9d5-124">Namespace</span></span>|<span data-ttu-id="bc9d5-125">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="bc9d5-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bc9d5-126">См. также</span><span class="sxs-lookup"><span data-stu-id="bc9d5-126">See Also</span></span>  
 <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>
