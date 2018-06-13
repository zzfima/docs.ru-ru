---
title: TransactionFlowBindingElement
ms.date: 03/30/2017
ms.assetid: 0a9656fe-2400-45ca-ad79-92715c8cf190
ms.openlocfilehash: c2fb32c4c693cbfc487ce89b36f013398cbdb703
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33485624"
---
# <a name="transactionflowbindingelement"></a><span data-ttu-id="c03df-102">TransactionFlowBindingElement</span><span class="sxs-lookup"><span data-stu-id="c03df-102">TransactionFlowBindingElement</span></span>
<span data-ttu-id="c03df-103">TransactionFlowBindingElement</span><span class="sxs-lookup"><span data-stu-id="c03df-103">TransactionFlowBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c03df-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c03df-104">Syntax</span></span>  
  
```  
class TransactionFlowBindingElement : BindingElement  
{  
  string IssuedTokens;  
  string TransactionProtocol;  
  boolean Transactions;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="c03df-105">Методы</span><span class="sxs-lookup"><span data-stu-id="c03df-105">Methods</span></span>  
 <span data-ttu-id="c03df-106">Класс TransactionFlowBindingElement не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="c03df-106">The TransactionFlowBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="c03df-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="c03df-107">Properties</span></span>  
 <span data-ttu-id="c03df-108">Класс TransactionFlowBindingElement имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="c03df-108">The TransactionFlowBindingElement class has the following properties:</span></span>  
  
### <a name="issuedtokens"></a><span data-ttu-id="c03df-109">IssuedTokens</span><span class="sxs-lookup"><span data-stu-id="c03df-109">IssuedTokens</span></span>  
 <span data-ttu-id="c03df-110">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="c03df-110">Data type: string</span></span>  
  
 <span data-ttu-id="c03df-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="c03df-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c03df-112">Задает требование для заголовка выданных маркеров безопасности (IssuedTokens из WS-Trust).</span><span class="sxs-lookup"><span data-stu-id="c03df-112">Specifies the requirement for an issued security tokens header (IssuedTokens from WS-Trust).</span></span>  
  
### <a name="transactionprotocol"></a><span data-ttu-id="c03df-113">TransactionProtocol</span><span class="sxs-lookup"><span data-stu-id="c03df-113">TransactionProtocol</span></span>  
 <span data-ttu-id="c03df-114">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="c03df-114">Data type: string</span></span>  
  
 <span data-ttu-id="c03df-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="c03df-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c03df-116">Протокол транзакций, используемый службой для передачи транзакций.</span><span class="sxs-lookup"><span data-stu-id="c03df-116">The transactions protocol used by the service to flow transactions.</span></span>  
  
### <a name="transactions"></a><span data-ttu-id="c03df-117">Транзакции</span><span class="sxs-lookup"><span data-stu-id="c03df-117">Transactions</span></span>  
 <span data-ttu-id="c03df-118">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="c03df-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="c03df-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="c03df-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c03df-120">Указывает, поддерживается ли входящая транзакция.</span><span class="sxs-lookup"><span data-stu-id="c03df-120">Indicates whether the incoming transaction is supported.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c03df-121">Требования</span><span class="sxs-lookup"><span data-stu-id="c03df-121">Requirements</span></span>  
  
|<span data-ttu-id="c03df-122">MOF</span><span class="sxs-lookup"><span data-stu-id="c03df-122">MOF</span></span>|<span data-ttu-id="c03df-123">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="c03df-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="c03df-124">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="c03df-124">Namespace</span></span>|<span data-ttu-id="c03df-125">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="c03df-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c03df-126">См. также</span><span class="sxs-lookup"><span data-stu-id="c03df-126">See Also</span></span>  
 <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>
