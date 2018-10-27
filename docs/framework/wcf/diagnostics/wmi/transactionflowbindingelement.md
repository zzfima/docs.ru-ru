---
title: TransactionFlowBindingElement
ms.date: 03/30/2017
ms.assetid: 0a9656fe-2400-45ca-ad79-92715c8cf190
ms.openlocfilehash: 027ace6ea9fc2a0e5ce63efa84e1a49c0ed2cd0a
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2018
ms.locfileid: "50188031"
---
# <a name="transactionflowbindingelement"></a><span data-ttu-id="84bf0-102">TransactionFlowBindingElement</span><span class="sxs-lookup"><span data-stu-id="84bf0-102">TransactionFlowBindingElement</span></span>
<span data-ttu-id="84bf0-103">TransactionFlowBindingElement</span><span class="sxs-lookup"><span data-stu-id="84bf0-103">TransactionFlowBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84bf0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="84bf0-104">Syntax</span></span>  
  
```csharp
class TransactionFlowBindingElement : BindingElement  
{  
  string IssuedTokens;  
  string TransactionProtocol;  
  boolean Transactions;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="84bf0-105">Методы</span><span class="sxs-lookup"><span data-stu-id="84bf0-105">Methods</span></span>  
 <span data-ttu-id="84bf0-106">Класс TransactionFlowBindingElement не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="84bf0-106">The TransactionFlowBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="84bf0-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="84bf0-107">Properties</span></span>  
 <span data-ttu-id="84bf0-108">Класс TransactionFlowBindingElement имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="84bf0-108">The TransactionFlowBindingElement class has the following properties:</span></span>  
  
### <a name="issuedtokens"></a><span data-ttu-id="84bf0-109">IssuedTokens</span><span class="sxs-lookup"><span data-stu-id="84bf0-109">IssuedTokens</span></span>  
 <span data-ttu-id="84bf0-110">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="84bf0-110">Data type: string</span></span>  
  
 <span data-ttu-id="84bf0-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="84bf0-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="84bf0-112">Задает требование для заголовка выданных маркеров безопасности (IssuedTokens из WS-Trust).</span><span class="sxs-lookup"><span data-stu-id="84bf0-112">Specifies the requirement for an issued security tokens header (IssuedTokens from WS-Trust).</span></span>  
  
### <a name="transactionprotocol"></a><span data-ttu-id="84bf0-113">TransactionProtocol</span><span class="sxs-lookup"><span data-stu-id="84bf0-113">TransactionProtocol</span></span>  
 <span data-ttu-id="84bf0-114">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="84bf0-114">Data type: string</span></span>  
  
 <span data-ttu-id="84bf0-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="84bf0-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="84bf0-116">Протокол транзакций, используемый службой для передачи транзакций.</span><span class="sxs-lookup"><span data-stu-id="84bf0-116">The transactions protocol used by the service to flow transactions.</span></span>  
  
### <a name="transactions"></a><span data-ttu-id="84bf0-117">Транзакции</span><span class="sxs-lookup"><span data-stu-id="84bf0-117">Transactions</span></span>  
 <span data-ttu-id="84bf0-118">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="84bf0-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="84bf0-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="84bf0-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="84bf0-120">Указывает, поддерживается ли входящая транзакция.</span><span class="sxs-lookup"><span data-stu-id="84bf0-120">Indicates whether the incoming transaction is supported.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84bf0-121">Требования</span><span class="sxs-lookup"><span data-stu-id="84bf0-121">Requirements</span></span>  
  
|<span data-ttu-id="84bf0-122">MOF</span><span class="sxs-lookup"><span data-stu-id="84bf0-122">MOF</span></span>|<span data-ttu-id="84bf0-123">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="84bf0-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="84bf0-124">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="84bf0-124">Namespace</span></span>|<span data-ttu-id="84bf0-125">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="84bf0-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="84bf0-126">См. также</span><span class="sxs-lookup"><span data-stu-id="84bf0-126">See Also</span></span>  
 <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>
