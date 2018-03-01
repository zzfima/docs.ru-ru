---
title: "Поддержка пространств имен в модели DOM"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f0548ead-0fed-41ee-b33e-117ba900d3bc
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 2b8135a55c537f480e0d595e127c2cad55e977ca
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="namespace-support-in-the-dom"></a><span data-ttu-id="d6712-102">Поддержка пространств имен в модели DOM</span><span class="sxs-lookup"><span data-stu-id="d6712-102">Namespace Support in the DOM</span></span>
<span data-ttu-id="d6712-103">Модель XML DOM полностью построена на пространствах имен.</span><span class="sxs-lookup"><span data-stu-id="d6712-103">The XML Document Object Model (DOM) is completely namespace-aware.</span></span> <span data-ttu-id="d6712-104">Поддерживаются только XML-документы, где определены пространства имен.</span><span class="sxs-lookup"><span data-stu-id="d6712-104">Only namespace-aware XML documents are supported.</span></span> <span data-ttu-id="d6712-105">По спецификации W3C приложения DOM, реализующие уровень 1, могут не учитывать пространства имен, а возможности уровня 2 модели DOM учитывают пространства имен.</span><span class="sxs-lookup"><span data-stu-id="d6712-105">The World Wide Web Consortium (W3C) specifies that DOM applications that implement Level 1 can be non-namespace-aware, and DOM Level 2 features are namespace-aware.</span></span> <span data-ttu-id="d6712-106">Однако в модели XML DOM все возможности учитывают пространства имен, независимо о того, соответствует ли метод рекомендации для уровня 1 или уровня 2 модели DOM.</span><span class="sxs-lookup"><span data-stu-id="d6712-106">However, all features in the XML DOM are namespace-aware, regardless if the method is from the Level 1 or Level 2 DOM Recommendation.</span></span>  
  
 <span data-ttu-id="d6712-107">Например, в среде без учета пространств имен вызов `setAttribute("A:b", "123")` согласно рекомендации для уровня 1 модели DOM не возвратит атрибут с префиксом `A` и локальным именем `b`.</span><span class="sxs-lookup"><span data-stu-id="d6712-107">For example, in a non-namespace-aware setting, calling `setAttribute("A:b", "123")`, as specified in the DOM Level 1 Recommendation, does not result in an attribute with a prefix of `A` and a local name of `b`.</span></span> <span data-ttu-id="d6712-108">Вместо этого будет получен атрибут со значением `A:b`.</span><span class="sxs-lookup"><span data-stu-id="d6712-108">It would result in an attribute with the value `A:b`.</span></span>  
  
 <span data-ttu-id="d6712-109">В среде с поддержкой пространств имен вызов метода `setAttribute("A:b", "123")` уровня 2 модели DOM возвратит атрибут с префиксом `A` и локальным именем `b`.</span><span class="sxs-lookup"><span data-stu-id="d6712-109">In a namespace-aware environment, the call to the DOM Level 2 `setAttribute("A:b", "123")` results in an attribute with a prefix of `A` and a local name of `b`.</span></span> <span data-ttu-id="d6712-110">Так работает модель DOM в платформе Microsoft .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d6712-110">This is how the Microsoft .NET Framework DOM works.</span></span>  
  
 <span data-ttu-id="d6712-111">Поэтому все методы, принимающие параметр имени, также принимают префикс, дополняющий имя.</span><span class="sxs-lookup"><span data-stu-id="d6712-111">Therefore, for all methods that take a name parameter, these methods also take a prefix to qualify the name.</span></span> <span data-ttu-id="d6712-112">Параметр имени, такой как `A:b` в методе **setAttribute** уровня 1 модели DOM, проходит синтаксический анализ следующим образом.</span><span class="sxs-lookup"><span data-stu-id="d6712-112">The name parameter, such as the `A:b` in the **setAttribute** DOM Level 1 method, is parsed as follows:</span></span>  
  
-   <span data-ttu-id="d6712-113">Если отсутствуют символы двоеточия (:), локальное имя получает значение параметра `name`, а строки для префикса и NamespaceURI будут пустыми.</span><span class="sxs-lookup"><span data-stu-id="d6712-113">If there are no colon (:) characters, then the local name is set to the `name` parameter, and the prefix and NamespaceURI are empty strings.</span></span>  
  
-   <span data-ttu-id="d6712-114">Если обнаружено двоеточие, имя разбивается на две части в зависимости от позиции первого символа двоеточия.</span><span class="sxs-lookup"><span data-stu-id="d6712-114">If a colon is found, then the name is split into two parts based on the position of the first colon character.</span></span> <span data-ttu-id="d6712-115">Префикс получает значение строки, расположенной перед двоеточием, а локальным именем становится строка, расположенная после двоеточия.</span><span class="sxs-lookup"><span data-stu-id="d6712-115">The prefix is set to the string found before the colon, and local name is set to the string found after the colon.</span></span> <span data-ttu-id="d6712-116">Для методов, не принимающих значение NamespaceURI, оно не разрешается и остается пустой строкой.</span><span class="sxs-lookup"><span data-stu-id="d6712-116">For methods that do not take a NamespaceURI value, the NamespaceURI is not resolved and remains set to empty string.</span></span> <span data-ttu-id="d6712-117">В противном случае NamespaceURI получает значение строки, переданной методу.</span><span class="sxs-lookup"><span data-stu-id="d6712-117">Otherwise, the NamespaceURI is set to the string passed to the method.</span></span> <span data-ttu-id="d6712-118">Если префикс не определен, метод **Save** и свойства **InnerXml** и **OuterXml** завершаются с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="d6712-118">If the prefix is undefined, then the **Save** method and **InnerXml** and **OuterXml** properties fail.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6712-119">См. также</span><span class="sxs-lookup"><span data-stu-id="d6712-119">See Also</span></span>  
 [<span data-ttu-id="d6712-120">Модель объектов документов XML (DOM)</span><span class="sxs-lookup"><span data-stu-id="d6712-120">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
