---
title: "Проверка имен XML-элементов и атрибутов при создании новых узлов"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b489f647-a175-4659-ada4-170058bb41d0
caps.latest.revision: "5"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c041d5d2830222f3fae09a39f1ea10eb08772388
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="xml-element-and-attribute-name-verification-when-creating-new-nodes"></a><span data-ttu-id="4b682-102">Проверка имен XML-элементов и атрибутов при создании новых узлов</span><span class="sxs-lookup"><span data-stu-id="4b682-102">XML Element and Attribute Name Verification when Creating New Nodes</span></span>
<span data-ttu-id="4b682-103">Модель XML DOM проверяет допустимость имен при создании новых узлов элементов или узлов атрибутов.</span><span class="sxs-lookup"><span data-stu-id="4b682-103">The XML Document Object Model (DOM) checks the validity of the names when creating new element nodes or attribute nodes.</span></span> <span data-ttu-id="4b682-104">Если имена содержат недопустимые символы, возникает исключение.</span><span class="sxs-lookup"><span data-stu-id="4b682-104">If the names contain illegal characters, an exception is thrown.</span></span> <span data-ttu-id="4b682-105">Чтобы убедиться, что имена являются допустимым и кодированный правильно, необходимо использовать **XmlConvert** класса имя кодирования и декодирования его на уровне приложения.</span><span class="sxs-lookup"><span data-stu-id="4b682-105">To ensure that names are valid and encoded correctly, you need to use the **XmlConvert** class to encode the name and decode it back at an application level.</span></span> <span data-ttu-id="4b682-106">**XmlWriter** содержит методы, которые выполняют дополнительную работу, чтобы убедиться в правильности XML-кода создается.</span><span class="sxs-lookup"><span data-stu-id="4b682-106">The **XmlWriter** has methods that do additional work to ensure well-formed XML is generated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b682-107">См. также</span><span class="sxs-lookup"><span data-stu-id="4b682-107">See Also</span></span>  
 [<span data-ttu-id="4b682-108">Модель объектов XML-документов (DOM)</span><span class="sxs-lookup"><span data-stu-id="4b682-108">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
