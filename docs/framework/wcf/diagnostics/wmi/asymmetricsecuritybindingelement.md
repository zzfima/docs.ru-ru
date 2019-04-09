---
title: AsymmetricSecurityBindingElement
ms.date: 03/30/2017
ms.assetid: 7bd3b6be-8f77-4927-93ae-6fa371893cca
ms.openlocfilehash: 0f86fc1b410753b5ec100f0a7d43de9badd1401b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59196051"
---
# <a name="asymmetricsecuritybindingelement"></a><span data-ttu-id="4f39b-102">AsymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="4f39b-102">AsymmetricSecurityBindingElement</span></span>
<span data-ttu-id="4f39b-103">AsymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="4f39b-103">AsymmetricSecurityBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f39b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4f39b-104">Syntax</span></span>  
  
```csharp
class AsymmetricSecurityBindingElement : SecurityBindingElement  
{  
  string MessageProtectionOrder;  
  boolean RequireSignatureConfirmation;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="4f39b-105">Методы</span><span class="sxs-lookup"><span data-stu-id="4f39b-105">Methods</span></span>  
 <span data-ttu-id="4f39b-106">Класс AsymmetricSecurityBindingElement не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="4f39b-106">The AsymmetricSecurityBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="4f39b-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="4f39b-107">Properties</span></span>  
 <span data-ttu-id="4f39b-108">Класс AsymmetricSecurityBindingElement имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="4f39b-108">The AsymmetricSecurityBindingElement class has the following properties:</span></span>  
  
### <a name="messageprotectionorder"></a><span data-ttu-id="4f39b-109">MessageProtectionOrder</span><span class="sxs-lookup"><span data-stu-id="4f39b-109">MessageProtectionOrder</span></span>  
 <span data-ttu-id="4f39b-110">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="4f39b-110">Data type: string</span></span>  
  
 <span data-ttu-id="4f39b-111">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="4f39b-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4f39b-112">Порядок шифрования и подписывания сообщений для данной привязки.</span><span class="sxs-lookup"><span data-stu-id="4f39b-112">The order of message encryption and signing for this binding.</span></span>  
  
### <a name="requiresignatureconfirmation"></a><span data-ttu-id="4f39b-113">RequireSignatureConfirmation</span><span class="sxs-lookup"><span data-stu-id="4f39b-113">RequireSignatureConfirmation</span></span>  
 <span data-ttu-id="4f39b-114">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="4f39b-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="4f39b-115">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="4f39b-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4f39b-116">Указывает, требует ли привязка подтверждения подписи.</span><span class="sxs-lookup"><span data-stu-id="4f39b-116">Whether the binding requires signature confirmation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f39b-117">Требования</span><span class="sxs-lookup"><span data-stu-id="4f39b-117">Requirements</span></span>  
  
|<span data-ttu-id="4f39b-118">MOF</span><span class="sxs-lookup"><span data-stu-id="4f39b-118">MOF</span></span>|<span data-ttu-id="4f39b-119">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="4f39b-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="4f39b-120">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="4f39b-120">Namespace</span></span>|<span data-ttu-id="4f39b-121">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="4f39b-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4f39b-122">См. также</span><span class="sxs-lookup"><span data-stu-id="4f39b-122">See also</span></span>

- <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>
