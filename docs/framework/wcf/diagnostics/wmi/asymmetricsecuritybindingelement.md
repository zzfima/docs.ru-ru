---
title: AsymmetricSecurityBindingElement
ms.date: 03/30/2017
ms.assetid: 7bd3b6be-8f77-4927-93ae-6fa371893cca
author: BrucePerlerMS
ms.openlocfilehash: 63af1c9a607cb9f81e2c0abf795ee2b3432cbf9c
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "47075061"
---
# <a name="asymmetricsecuritybindingelement"></a><span data-ttu-id="46a49-102">AsymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="46a49-102">AsymmetricSecurityBindingElement</span></span>
<span data-ttu-id="46a49-103">AsymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="46a49-103">AsymmetricSecurityBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46a49-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="46a49-104">Syntax</span></span>  
  
```  
class AsymmetricSecurityBindingElement : SecurityBindingElement  
{  
  string MessageProtectionOrder;  
  boolean RequireSignatureConfirmation;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="46a49-105">Методы</span><span class="sxs-lookup"><span data-stu-id="46a49-105">Methods</span></span>  
 <span data-ttu-id="46a49-106">Класс AsymmetricSecurityBindingElement не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="46a49-106">The AsymmetricSecurityBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="46a49-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="46a49-107">Properties</span></span>  
 <span data-ttu-id="46a49-108">Класс AsymmetricSecurityBindingElement имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="46a49-108">The AsymmetricSecurityBindingElement class has the following properties:</span></span>  
  
### <a name="messageprotectionorder"></a><span data-ttu-id="46a49-109">MessageProtectionOrder</span><span class="sxs-lookup"><span data-stu-id="46a49-109">MessageProtectionOrder</span></span>  
 <span data-ttu-id="46a49-110">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="46a49-110">Data type: string</span></span>  
  
 <span data-ttu-id="46a49-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="46a49-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="46a49-112">Порядок шифрования и подписывания сообщений для данной привязки.</span><span class="sxs-lookup"><span data-stu-id="46a49-112">The order of message encryption and signing for this binding.</span></span>  
  
### <a name="requiresignatureconfirmation"></a><span data-ttu-id="46a49-113">RequireSignatureConfirmation</span><span class="sxs-lookup"><span data-stu-id="46a49-113">RequireSignatureConfirmation</span></span>  
 <span data-ttu-id="46a49-114">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="46a49-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="46a49-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="46a49-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="46a49-116">Указывает, требует ли привязка подтверждения подписи.</span><span class="sxs-lookup"><span data-stu-id="46a49-116">Whether the binding requires signature confirmation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46a49-117">Требования</span><span class="sxs-lookup"><span data-stu-id="46a49-117">Requirements</span></span>  
  
|<span data-ttu-id="46a49-118">MOF</span><span class="sxs-lookup"><span data-stu-id="46a49-118">MOF</span></span>|<span data-ttu-id="46a49-119">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="46a49-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="46a49-120">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="46a49-120">Namespace</span></span>|<span data-ttu-id="46a49-121">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="46a49-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="46a49-122">См. также</span><span class="sxs-lookup"><span data-stu-id="46a49-122">See Also</span></span>  
 <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>
