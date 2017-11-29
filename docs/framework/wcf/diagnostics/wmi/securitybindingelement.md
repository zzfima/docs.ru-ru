---
title: SecurityBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ef93b6e6-3524-48a8-94d3-c8837f1872f9
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: b567c173c5a04421bce57585d96b8b45144c5625
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="securitybindingelement"></a><span data-ttu-id="f2c31-102">SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="f2c31-102">SecurityBindingElement</span></span>
<span data-ttu-id="f2c31-103">SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="f2c31-103">SecurityBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2c31-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f2c31-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="f2c31-105">Методы</span><span class="sxs-lookup"><span data-stu-id="f2c31-105">Methods</span></span>  
 <span data-ttu-id="f2c31-106">Класс SecurityBindingElement не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="f2c31-106">The SecurityBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="f2c31-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="f2c31-107">Properties</span></span>  
 <span data-ttu-id="f2c31-108">Класс SecurityBindingElement имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="f2c31-108">The SecurityBindingElement class has the following properties:</span></span>  
  
### <a name="defaultalgorithmsuite"></a><span data-ttu-id="f2c31-109">DefaultAlgorithmSuite</span><span class="sxs-lookup"><span data-stu-id="f2c31-109">DefaultAlgorithmSuite</span></span>  
 <span data-ttu-id="f2c31-110">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="f2c31-110">Data type: string</span></span>  
  
 <span data-ttu-id="f2c31-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="f2c31-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f2c31-112">Задает алгоритмы, используемые в сочетании с привязкой.</span><span class="sxs-lookup"><span data-stu-id="f2c31-112">Specifies the algorithms to use with the binding.</span></span>  
  
### <a name="includetimestamp"></a><span data-ttu-id="f2c31-113">IncludeTimestamp</span><span class="sxs-lookup"><span data-stu-id="f2c31-113">IncludeTimestamp</span></span>  
 <span data-ttu-id="f2c31-114">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="f2c31-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="f2c31-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="f2c31-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f2c31-116">Логическое значение, указывающее, будет ли в каждое сообщение вноситься отметка времени.</span><span class="sxs-lookup"><span data-stu-id="f2c31-116">A Boolean value that specifies whether each message contains a timestamp.</span></span>  
  
### <a name="keyentropymode"></a><span data-ttu-id="f2c31-117">KeyEntropyMode</span><span class="sxs-lookup"><span data-stu-id="f2c31-117">KeyEntropyMode</span></span>  
 <span data-ttu-id="f2c31-118">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="f2c31-118">Data type: string</span></span>  
  
 <span data-ttu-id="f2c31-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="f2c31-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f2c31-120">Источник энтропии, используемый для создания ключей.</span><span class="sxs-lookup"><span data-stu-id="f2c31-120">The source of entropy used to create keys.</span></span>  
  
### <a name="localservicesecuritysettings"></a><span data-ttu-id="f2c31-121">LocalServiceSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="f2c31-121">LocalServiceSecuritySettings</span></span>  
 <span data-ttu-id="f2c31-122">Тип данных: LocalServiceSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="f2c31-122">Data type: LocalServiceSecuritySettings</span></span>  
  
 <span data-ttu-id="f2c31-123">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="f2c31-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f2c31-124">Свойства безопасности для локальной службы, соответствующие данной привязке.</span><span class="sxs-lookup"><span data-stu-id="f2c31-124">The binding specific security properties for the local service.</span></span>  
  
### <a name="messagesecurityversion"></a><span data-ttu-id="f2c31-125">MessageSecurityVersion</span><span class="sxs-lookup"><span data-stu-id="f2c31-125">MessageSecurityVersion</span></span>  
 <span data-ttu-id="f2c31-126">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="f2c31-126">Data type: string</span></span>  
  
 <span data-ttu-id="f2c31-127">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="f2c31-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f2c31-128">Версия, используемая для безопасности сообщения.</span><span class="sxs-lookup"><span data-stu-id="f2c31-128">The version used for message security.</span></span>  
  
### <a name="securityheaderlayout"></a><span data-ttu-id="f2c31-129">SecurityHeaderLayout</span><span class="sxs-lookup"><span data-stu-id="f2c31-129">SecurityHeaderLayout</span></span>  
 <span data-ttu-id="f2c31-130">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="f2c31-130">Data type: string</span></span>  
  
 <span data-ttu-id="f2c31-131">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="f2c31-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f2c31-132">Порядок элементов в заголовке безопасности для данной привязки.</span><span class="sxs-lookup"><span data-stu-id="f2c31-132">The order of elements in the security header for this binding.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2c31-133">Требования</span><span class="sxs-lookup"><span data-stu-id="f2c31-133">Requirements</span></span>  
  
|<span data-ttu-id="f2c31-134">MOF</span><span class="sxs-lookup"><span data-stu-id="f2c31-134">MOF</span></span>|<span data-ttu-id="f2c31-135">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="f2c31-135">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="f2c31-136">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="f2c31-136">Namespace</span></span>|<span data-ttu-id="f2c31-137">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="f2c31-137">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f2c31-138">См. также</span><span class="sxs-lookup"><span data-stu-id="f2c31-138">See Also</span></span>  
 <xref:System.ServiceModel.Channels.SecurityBindingElement>
