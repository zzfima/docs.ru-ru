---
title: Пример XML-файла. Числовые данные в пространстве имен3
ms.date: 07/20/2015
ms.assetid: 51750cab-3c66-4511-90fb-b9d211308d31
ms.openlocfilehash: 5a752f477d17cee50b98bc88bd39cabda2bd3bf6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33329008"
---
# <a name="sample-xml-file-numerical-data-in-a-namespace"></a><span data-ttu-id="957c4-102">Пример XML-файла. Числовые данные пространстве имен</span><span class="sxs-lookup"><span data-stu-id="957c4-102">Sample XML File: Numerical Data in a Namespace</span></span>
<span data-ttu-id="957c4-103">Следующий XML-файл используется в различных примерах в документации [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="957c4-103">The following XML file is used in various examples in the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] documentation.</span></span> <span data-ttu-id="957c4-104">Этот файл содержит числовые данные для суммирования, вычисления средних значений и группирования.</span><span class="sxs-lookup"><span data-stu-id="957c4-104">This file contains numerical data for summing, averaging, and grouping.</span></span> <span data-ttu-id="957c4-105">XML располагается в пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="957c4-105">The XML is in a namespace.</span></span>  
  
## <a name="data"></a><span data-ttu-id="957c4-106">Данные</span><span class="sxs-lookup"><span data-stu-id="957c4-106">Data</span></span>  
  
```xml  
<Root xmlns='http://www.adatum.com'>  
  <TaxRate>7.25</TaxRate>  
  <Data>  
    <Category>A</Category>  
    <Quantity>3</Quantity>  
    <Price>24.50</Price>  
  </Data>  
  <Data>  
    <Category>B</Category>  
    <Quantity>1</Quantity>  
    <Price>89.99</Price>  
  </Data>  
  <Data>  
    <Category>A</Category>  
    <Quantity>5</Quantity>  
    <Price>4.95</Price>  
  </Data>  
  <Data>  
    <Category>A</Category>  
    <Quantity>3</Quantity>  
    <Price>66.00</Price>  
  </Data>  
  <Data>  
    <Category>B</Category>  
    <Quantity>10</Quantity>  
    <Price>.99</Price>  
  </Data>  
  <Data>  
    <Category>A</Category>  
    <Quantity>15</Quantity>  
    <Price>29.00</Price>  
  </Data>  
  <Data>  
    <Category>B</Category>  
    <Quantity>8</Quantity>  
    <Price>6.99</Price>  
  </Data>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="957c4-107">См. также</span><span class="sxs-lookup"><span data-stu-id="957c4-107">See Also</span></span>  
 [<span data-ttu-id="957c4-108">Примеры XML-документов (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="957c4-108">Sample XML Documents (LINQ to XML)</span></span>](../../../../csharp/programming-guide/concepts/linq/sample-xml-documents-linq-to-xml.md)
