---
title: Проверка имен XML-элементов и атрибутов при создании новых узлов
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: b489f647-a175-4659-ada4-170058bb41d0
author: mairaw
ms.author: mairaw
ms.openlocfilehash: de11c190310dec90bd23d044f77d0c38e3a34fcf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="xml-element-and-attribute-name-verification-when-creating-new-nodes"></a><span data-ttu-id="25782-102">Проверка имен XML-элементов и атрибутов при создании новых узлов</span><span class="sxs-lookup"><span data-stu-id="25782-102">XML Element and Attribute Name Verification when Creating New Nodes</span></span>
<span data-ttu-id="25782-103">Модель XML DOM проверяет допустимость имен при создании новых узлов элементов или узлов атрибутов.</span><span class="sxs-lookup"><span data-stu-id="25782-103">The XML Document Object Model (DOM) checks the validity of the names when creating new element nodes or attribute nodes.</span></span> <span data-ttu-id="25782-104">Если имена содержат недопустимые символы, возникает исключение.</span><span class="sxs-lookup"><span data-stu-id="25782-104">If the names contain illegal characters, an exception is thrown.</span></span> <span data-ttu-id="25782-105">Чтобы гарантировать допустимость и правильную кодировку имен, необходимо использовать класс **XmlConvert** для кодирования и декодирования имен на уровне приложения.</span><span class="sxs-lookup"><span data-stu-id="25782-105">To ensure that names are valid and encoded correctly, you need to use the **XmlConvert** class to encode the name and decode it back at an application level.</span></span> <span data-ttu-id="25782-106">Класс **XmlWriter** содержит методы, которые выполняют дополнительную работу, чтобы обеспечить формирование XML-документов правильного формата.</span><span class="sxs-lookup"><span data-stu-id="25782-106">The **XmlWriter** has methods that do additional work to ensure well-formed XML is generated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25782-107">См. также</span><span class="sxs-lookup"><span data-stu-id="25782-107">See Also</span></span>  
 [<span data-ttu-id="25782-108">Модель объектов документов XML (DOM)</span><span class="sxs-lookup"><span data-stu-id="25782-108">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
