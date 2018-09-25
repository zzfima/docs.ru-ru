---
title: SecurityBindingElement
ms.date: 03/30/2017
ms.assetid: ef93b6e6-3524-48a8-94d3-c8837f1872f9
author: BrucePerlerMS
ms.openlocfilehash: 19c65b3028ad63b8a78205d00f44cc32322648d5
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "47069978"
---
# <a name="securitybindingelement"></a><span data-ttu-id="91dd8-102">SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="91dd8-102">SecurityBindingElement</span></span>
<span data-ttu-id="91dd8-103">SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="91dd8-103">SecurityBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91dd8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="91dd8-104">Syntax</span></span>  
  
```  
class SecurityBindingElement : BindingElement  
{  
  string DefaultAlgorithmSuite;  
  boolean IncludeTimestamp;  
  string KeyEntropyMode;  
  LocalServiceSecuritySettings LocalServiceSecuritySettings;  
  string MessageSecurityVersion;  
  string SecurityHeaderLayout;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="91dd8-105">Методы</span><span class="sxs-lookup"><span data-stu-id="91dd8-105">Methods</span></span>  
 <span data-ttu-id="91dd8-106">Класс SecurityBindingElement не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="91dd8-106">The SecurityBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="91dd8-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="91dd8-107">Properties</span></span>  
 <span data-ttu-id="91dd8-108">Класс SecurityBindingElement имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="91dd8-108">The SecurityBindingElement class has the following properties:</span></span>  
  
### <a name="defaultalgorithmsuite"></a><span data-ttu-id="91dd8-109">DefaultAlgorithmSuite</span><span class="sxs-lookup"><span data-stu-id="91dd8-109">DefaultAlgorithmSuite</span></span>  
 <span data-ttu-id="91dd8-110">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="91dd8-110">Data type: string</span></span>  
  
 <span data-ttu-id="91dd8-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="91dd8-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="91dd8-112">Задает алгоритмы, используемые в сочетании с привязкой.</span><span class="sxs-lookup"><span data-stu-id="91dd8-112">Specifies the algorithms to use with the binding.</span></span>  
  
### <a name="includetimestamp"></a><span data-ttu-id="91dd8-113">IncludeTimestamp</span><span class="sxs-lookup"><span data-stu-id="91dd8-113">IncludeTimestamp</span></span>  
 <span data-ttu-id="91dd8-114">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="91dd8-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="91dd8-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="91dd8-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="91dd8-116">Логическое значение, указывающее, будет ли в каждое сообщение вноситься отметка времени.</span><span class="sxs-lookup"><span data-stu-id="91dd8-116">A Boolean value that specifies whether each message contains a timestamp.</span></span>  
  
### <a name="keyentropymode"></a><span data-ttu-id="91dd8-117">KeyEntropyMode</span><span class="sxs-lookup"><span data-stu-id="91dd8-117">KeyEntropyMode</span></span>  
 <span data-ttu-id="91dd8-118">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="91dd8-118">Data type: string</span></span>  
  
 <span data-ttu-id="91dd8-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="91dd8-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="91dd8-120">Источник энтропии, используемый для создания ключей.</span><span class="sxs-lookup"><span data-stu-id="91dd8-120">The source of entropy used to create keys.</span></span>  
  
### <a name="localservicesecuritysettings"></a><span data-ttu-id="91dd8-121">LocalServiceSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="91dd8-121">LocalServiceSecuritySettings</span></span>  
 <span data-ttu-id="91dd8-122">Тип данных: LocalServiceSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="91dd8-122">Data type: LocalServiceSecuritySettings</span></span>  
  
 <span data-ttu-id="91dd8-123">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="91dd8-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="91dd8-124">Свойства безопасности для локальной службы, соответствующие данной привязке.</span><span class="sxs-lookup"><span data-stu-id="91dd8-124">The binding specific security properties for the local service.</span></span>  
  
### <a name="messagesecurityversion"></a><span data-ttu-id="91dd8-125">MessageSecurityVersion</span><span class="sxs-lookup"><span data-stu-id="91dd8-125">MessageSecurityVersion</span></span>  
 <span data-ttu-id="91dd8-126">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="91dd8-126">Data type: string</span></span>  
  
 <span data-ttu-id="91dd8-127">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="91dd8-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="91dd8-128">Версия, используемая для безопасности сообщения.</span><span class="sxs-lookup"><span data-stu-id="91dd8-128">The version used for message security.</span></span>  
  
### <a name="securityheaderlayout"></a><span data-ttu-id="91dd8-129">SecurityHeaderLayout</span><span class="sxs-lookup"><span data-stu-id="91dd8-129">SecurityHeaderLayout</span></span>  
 <span data-ttu-id="91dd8-130">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="91dd8-130">Data type: string</span></span>  
  
 <span data-ttu-id="91dd8-131">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="91dd8-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="91dd8-132">Порядок элементов в заголовке безопасности для данной привязки.</span><span class="sxs-lookup"><span data-stu-id="91dd8-132">The order of elements in the security header for this binding.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="91dd8-133">Требования</span><span class="sxs-lookup"><span data-stu-id="91dd8-133">Requirements</span></span>  
  
|<span data-ttu-id="91dd8-134">MOF</span><span class="sxs-lookup"><span data-stu-id="91dd8-134">MOF</span></span>|<span data-ttu-id="91dd8-135">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="91dd8-135">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="91dd8-136">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="91dd8-136">Namespace</span></span>|<span data-ttu-id="91dd8-137">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="91dd8-137">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="91dd8-138">См. также</span><span class="sxs-lookup"><span data-stu-id="91dd8-138">See Also</span></span>  
 <xref:System.ServiceModel.Channels.SecurityBindingElement>
