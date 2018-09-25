---
title: SymmetricSecurityBindingElement
ms.date: 03/30/2017
ms.assetid: b2e182b6-c041-4d80-a926-6058068d9f79
author: BrucePerlerMS
ms.openlocfilehash: 180b64f6f37e5c765585e52b292319816618be28
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "47076526"
---
# <a name="symmetricsecuritybindingelement"></a><span data-ttu-id="b1c32-102">SymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="b1c32-102">SymmetricSecurityBindingElement</span></span>
<span data-ttu-id="b1c32-103">SymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="b1c32-103">SymmetricSecurityBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1c32-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b1c32-104">Syntax</span></span>  
  
```  
class SymmetricSecurityBindingElement : SecurityBindingElement  
{  
  string MessageProtectionOrder;  
  boolean RequireSignatureConfirmation;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="b1c32-105">Методы</span><span class="sxs-lookup"><span data-stu-id="b1c32-105">Methods</span></span>  
 <span data-ttu-id="b1c32-106">Класс SymmetricSecurityBindingElement не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="b1c32-106">The SymmetricSecurityBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="b1c32-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="b1c32-107">Properties</span></span>  
 <span data-ttu-id="b1c32-108">Класс SymmetricSecurityBindingElement имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="b1c32-108">The SymmetricSecurityBindingElement class has the following properties:</span></span>  
  
### <a name="messageprotectionorder"></a><span data-ttu-id="b1c32-109">MessageProtectionOrder</span><span class="sxs-lookup"><span data-stu-id="b1c32-109">MessageProtectionOrder</span></span>  
 <span data-ttu-id="b1c32-110">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="b1c32-110">Data type: string</span></span>  
  
 <span data-ttu-id="b1c32-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="b1c32-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b1c32-112">Порядок шифрования и подписывания сообщений для данной привязки.</span><span class="sxs-lookup"><span data-stu-id="b1c32-112">The order of message encryption and signing for this binding.</span></span>  
  
### <a name="requiresignatureconfirmation"></a><span data-ttu-id="b1c32-113">RequireSignatureConfirmation</span><span class="sxs-lookup"><span data-stu-id="b1c32-113">RequireSignatureConfirmation</span></span>  
 <span data-ttu-id="b1c32-114">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="b1c32-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="b1c32-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="b1c32-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b1c32-116">Указывает, требует ли привязка подтверждения подписи.</span><span class="sxs-lookup"><span data-stu-id="b1c32-116">Whether the binding requires signature confirmation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b1c32-117">Требования</span><span class="sxs-lookup"><span data-stu-id="b1c32-117">Requirements</span></span>  
  
|<span data-ttu-id="b1c32-118">MOF</span><span class="sxs-lookup"><span data-stu-id="b1c32-118">MOF</span></span>|<span data-ttu-id="b1c32-119">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="b1c32-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="b1c32-120">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="b1c32-120">Namespace</span></span>|<span data-ttu-id="b1c32-121">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="b1c32-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b1c32-122">См. также</span><span class="sxs-lookup"><span data-stu-id="b1c32-122">See Also</span></span>  
 <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>
