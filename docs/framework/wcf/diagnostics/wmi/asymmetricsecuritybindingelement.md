---
title: AsymmetricSecurityBindingElement
ms.date: 03/30/2017
ms.assetid: 7bd3b6be-8f77-4927-93ae-6fa371893cca
ms.openlocfilehash: 076313548828f1fbce9c68b48c0fa7db9cca095f
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2018
ms.locfileid: "50185122"
---
# <a name="asymmetricsecuritybindingelement"></a><span data-ttu-id="eafb9-102">AsymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="eafb9-102">AsymmetricSecurityBindingElement</span></span>
<span data-ttu-id="eafb9-103">AsymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="eafb9-103">AsymmetricSecurityBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eafb9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="eafb9-104">Syntax</span></span>  
  
```csharp
class AsymmetricSecurityBindingElement : SecurityBindingElement  
{  
  string MessageProtectionOrder;  
  boolean RequireSignatureConfirmation;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="eafb9-105">Методы</span><span class="sxs-lookup"><span data-stu-id="eafb9-105">Methods</span></span>  
 <span data-ttu-id="eafb9-106">Класс AsymmetricSecurityBindingElement не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="eafb9-106">The AsymmetricSecurityBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="eafb9-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="eafb9-107">Properties</span></span>  
 <span data-ttu-id="eafb9-108">Класс AsymmetricSecurityBindingElement имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="eafb9-108">The AsymmetricSecurityBindingElement class has the following properties:</span></span>  
  
### <a name="messageprotectionorder"></a><span data-ttu-id="eafb9-109">MessageProtectionOrder</span><span class="sxs-lookup"><span data-stu-id="eafb9-109">MessageProtectionOrder</span></span>  
 <span data-ttu-id="eafb9-110">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="eafb9-110">Data type: string</span></span>  
  
 <span data-ttu-id="eafb9-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="eafb9-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="eafb9-112">Порядок шифрования и подписывания сообщений для данной привязки.</span><span class="sxs-lookup"><span data-stu-id="eafb9-112">The order of message encryption and signing for this binding.</span></span>  
  
### <a name="requiresignatureconfirmation"></a><span data-ttu-id="eafb9-113">RequireSignatureConfirmation</span><span class="sxs-lookup"><span data-stu-id="eafb9-113">RequireSignatureConfirmation</span></span>  
 <span data-ttu-id="eafb9-114">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="eafb9-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="eafb9-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="eafb9-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="eafb9-116">Указывает, требует ли привязка подтверждения подписи.</span><span class="sxs-lookup"><span data-stu-id="eafb9-116">Whether the binding requires signature confirmation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eafb9-117">Требования</span><span class="sxs-lookup"><span data-stu-id="eafb9-117">Requirements</span></span>  
  
|<span data-ttu-id="eafb9-118">MOF</span><span class="sxs-lookup"><span data-stu-id="eafb9-118">MOF</span></span>|<span data-ttu-id="eafb9-119">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="eafb9-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="eafb9-120">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="eafb9-120">Namespace</span></span>|<span data-ttu-id="eafb9-121">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="eafb9-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="eafb9-122">См. также</span><span class="sxs-lookup"><span data-stu-id="eafb9-122">See Also</span></span>  
 <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>
