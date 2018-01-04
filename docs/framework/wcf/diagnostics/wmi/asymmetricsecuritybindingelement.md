---
title: AsymmetricSecurityBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7bd3b6be-8f77-4927-93ae-6fa371893cca
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 82e5365a440d103727f354e682d0ebecb5f46a46
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="asymmetricsecuritybindingelement"></a><span data-ttu-id="8eaa1-102">AsymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="8eaa1-102">AsymmetricSecurityBindingElement</span></span>
<span data-ttu-id="8eaa1-103">AsymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="8eaa1-103">AsymmetricSecurityBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8eaa1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8eaa1-104">Syntax</span></span>  
  
```  
class AsymmetricSecurityBindingElement : SecurityBindingElement  
{  
  string MessageProtectionOrder;  
  boolean RequireSignatureConfirmation;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="8eaa1-105">Методы</span><span class="sxs-lookup"><span data-stu-id="8eaa1-105">Methods</span></span>  
 <span data-ttu-id="8eaa1-106">Класс AsymmetricSecurityBindingElement не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="8eaa1-106">The AsymmetricSecurityBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="8eaa1-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="8eaa1-107">Properties</span></span>  
 <span data-ttu-id="8eaa1-108">Класс AsymmetricSecurityBindingElement имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="8eaa1-108">The AsymmetricSecurityBindingElement class has the following properties:</span></span>  
  
### <a name="messageprotectionorder"></a><span data-ttu-id="8eaa1-109">MessageProtectionOrder</span><span class="sxs-lookup"><span data-stu-id="8eaa1-109">MessageProtectionOrder</span></span>  
 <span data-ttu-id="8eaa1-110">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="8eaa1-110">Data type: string</span></span>  
  
 <span data-ttu-id="8eaa1-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="8eaa1-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8eaa1-112">Порядок шифрования и подписывания сообщений для данной привязки.</span><span class="sxs-lookup"><span data-stu-id="8eaa1-112">The order of message encryption and signing for this binding.</span></span>  
  
### <a name="requiresignatureconfirmation"></a><span data-ttu-id="8eaa1-113">RequireSignatureConfirmation</span><span class="sxs-lookup"><span data-stu-id="8eaa1-113">RequireSignatureConfirmation</span></span>  
 <span data-ttu-id="8eaa1-114">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="8eaa1-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="8eaa1-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="8eaa1-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8eaa1-116">Указывает, требует ли привязка подтверждения подписи.</span><span class="sxs-lookup"><span data-stu-id="8eaa1-116">Whether the binding requires signature confirmation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8eaa1-117">Требования</span><span class="sxs-lookup"><span data-stu-id="8eaa1-117">Requirements</span></span>  
  
|<span data-ttu-id="8eaa1-118">MOF</span><span class="sxs-lookup"><span data-stu-id="8eaa1-118">MOF</span></span>|<span data-ttu-id="8eaa1-119">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="8eaa1-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="8eaa1-120">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="8eaa1-120">Namespace</span></span>|<span data-ttu-id="8eaa1-121">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="8eaa1-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8eaa1-122">См. также</span><span class="sxs-lookup"><span data-stu-id="8eaa1-122">See Also</span></span>  
 <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>
