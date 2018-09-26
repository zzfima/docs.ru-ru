---
title: SymmetricSecurityBindingElement
ms.date: 03/30/2017
ms.assetid: b2e182b6-c041-4d80-a926-6058068d9f79
author: BrucePerlerMS
ms.openlocfilehash: 180b64f6f37e5c765585e52b292319816618be28
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/26/2018
ms.locfileid: "47198856"
---
# <a name="symmetricsecuritybindingelement"></a><span data-ttu-id="5e6fe-102">SymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="5e6fe-102">SymmetricSecurityBindingElement</span></span>
<span data-ttu-id="5e6fe-103">SymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="5e6fe-103">SymmetricSecurityBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e6fe-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5e6fe-104">Syntax</span></span>  
  
```  
class SymmetricSecurityBindingElement : SecurityBindingElement  
{  
  string MessageProtectionOrder;  
  boolean RequireSignatureConfirmation;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="5e6fe-105">Методы</span><span class="sxs-lookup"><span data-stu-id="5e6fe-105">Methods</span></span>  
 <span data-ttu-id="5e6fe-106">Класс SymmetricSecurityBindingElement не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="5e6fe-106">The SymmetricSecurityBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="5e6fe-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="5e6fe-107">Properties</span></span>  
 <span data-ttu-id="5e6fe-108">Класс SymmetricSecurityBindingElement имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="5e6fe-108">The SymmetricSecurityBindingElement class has the following properties:</span></span>  
  
### <a name="messageprotectionorder"></a><span data-ttu-id="5e6fe-109">MessageProtectionOrder</span><span class="sxs-lookup"><span data-stu-id="5e6fe-109">MessageProtectionOrder</span></span>  
 <span data-ttu-id="5e6fe-110">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="5e6fe-110">Data type: string</span></span>  
  
 <span data-ttu-id="5e6fe-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="5e6fe-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5e6fe-112">Порядок шифрования и подписывания сообщений для данной привязки.</span><span class="sxs-lookup"><span data-stu-id="5e6fe-112">The order of message encryption and signing for this binding.</span></span>  
  
### <a name="requiresignatureconfirmation"></a><span data-ttu-id="5e6fe-113">RequireSignatureConfirmation</span><span class="sxs-lookup"><span data-stu-id="5e6fe-113">RequireSignatureConfirmation</span></span>  
 <span data-ttu-id="5e6fe-114">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="5e6fe-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="5e6fe-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="5e6fe-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5e6fe-116">Указывает, требует ли привязка подтверждения подписи.</span><span class="sxs-lookup"><span data-stu-id="5e6fe-116">Whether the binding requires signature confirmation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e6fe-117">Требования</span><span class="sxs-lookup"><span data-stu-id="5e6fe-117">Requirements</span></span>  
  
|<span data-ttu-id="5e6fe-118">MOF</span><span class="sxs-lookup"><span data-stu-id="5e6fe-118">MOF</span></span>|<span data-ttu-id="5e6fe-119">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="5e6fe-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="5e6fe-120">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="5e6fe-120">Namespace</span></span>|<span data-ttu-id="5e6fe-121">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="5e6fe-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5e6fe-122">См. также</span><span class="sxs-lookup"><span data-stu-id="5e6fe-122">See Also</span></span>  
 <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>
