---
title: SymmetricSecurityBindingElement
ms.date: 03/30/2017
ms.assetid: b2e182b6-c041-4d80-a926-6058068d9f79
author: BrucePerlerMS
ms.openlocfilehash: e633ae19cd17930fb140a93ffd0910c7ed8efea4
ms.sourcegitcommit: e42d09e5966dd9fd02847d3e7eeb4ec0877069f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2018
ms.locfileid: "49374437"
---
# <a name="symmetricsecuritybindingelement"></a><span data-ttu-id="bed03-102">SymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="bed03-102">SymmetricSecurityBindingElement</span></span>
<span data-ttu-id="bed03-103">SymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="bed03-103">SymmetricSecurityBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bed03-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bed03-104">Syntax</span></span>  
  
```csharp
class SymmetricSecurityBindingElement : SecurityBindingElement  
{  
  string MessageProtectionOrder;  
  boolean RequireSignatureConfirmation;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="bed03-105">Методы</span><span class="sxs-lookup"><span data-stu-id="bed03-105">Methods</span></span>  
 <span data-ttu-id="bed03-106">Класс SymmetricSecurityBindingElement не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="bed03-106">The SymmetricSecurityBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="bed03-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="bed03-107">Properties</span></span>  
 <span data-ttu-id="bed03-108">Класс SymmetricSecurityBindingElement имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="bed03-108">The SymmetricSecurityBindingElement class has the following properties:</span></span>  
  
### <a name="messageprotectionorder"></a><span data-ttu-id="bed03-109">MessageProtectionOrder</span><span class="sxs-lookup"><span data-stu-id="bed03-109">MessageProtectionOrder</span></span>  
 <span data-ttu-id="bed03-110">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="bed03-110">Data type: string</span></span>  
  
 <span data-ttu-id="bed03-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="bed03-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bed03-112">Порядок шифрования и подписывания сообщений для данной привязки.</span><span class="sxs-lookup"><span data-stu-id="bed03-112">The order of message encryption and signing for this binding.</span></span>  
  
### <a name="requiresignatureconfirmation"></a><span data-ttu-id="bed03-113">RequireSignatureConfirmation</span><span class="sxs-lookup"><span data-stu-id="bed03-113">RequireSignatureConfirmation</span></span>  
 <span data-ttu-id="bed03-114">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="bed03-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="bed03-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="bed03-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bed03-116">Указывает, требует ли привязка подтверждения подписи.</span><span class="sxs-lookup"><span data-stu-id="bed03-116">Whether the binding requires signature confirmation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bed03-117">Требования</span><span class="sxs-lookup"><span data-stu-id="bed03-117">Requirements</span></span>  
  
|<span data-ttu-id="bed03-118">MOF</span><span class="sxs-lookup"><span data-stu-id="bed03-118">MOF</span></span>|<span data-ttu-id="bed03-119">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="bed03-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="bed03-120">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="bed03-120">Namespace</span></span>|<span data-ttu-id="bed03-121">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="bed03-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bed03-122">См. также</span><span class="sxs-lookup"><span data-stu-id="bed03-122">See Also</span></span>  
 <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>
