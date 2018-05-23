---
title: Преобразование типов XML-данных
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: a2aa99ba-8239-4818-9281-f1d72ee40bde
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c22ebed1127be6a32a09b428b977b1ba9ca0a7eb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="conversion-of-xml-data-types"></a><span data-ttu-id="80e6f-102">Преобразование типов XML-данных</span><span class="sxs-lookup"><span data-stu-id="80e6f-102">Conversion of XML Data Types</span></span>
<span data-ttu-id="80e6f-103">Большая часть методов класса **XmlConvert** используются для преобразования данных в строки и строго типизированные форматы.</span><span class="sxs-lookup"><span data-stu-id="80e6f-103">The majority of the methods found in an **XmlConvert** class are used to convert data between strings and strongly-typed formats.</span></span> <span data-ttu-id="80e6f-104">Методы не зависят от языковых стандартов.</span><span class="sxs-lookup"><span data-stu-id="80e6f-104">Methods are locale independent.</span></span> <span data-ttu-id="80e6f-105">Это означает, что при преобразовании они не принимают во внимание параметры языковых стандартов.</span><span class="sxs-lookup"><span data-stu-id="80e6f-105">This means that they do not take into account any locale settings when doing conversion.</span></span>  
  
## <a name="reading-string-as-types"></a><span data-ttu-id="80e6f-106">Считывание строк как типов</span><span class="sxs-lookup"><span data-stu-id="80e6f-106">Reading String as types</span></span>  
 <span data-ttu-id="80e6f-107">Следующий образец считывает строку и преобразует ее в тип **DateTime**.</span><span class="sxs-lookup"><span data-stu-id="80e6f-107">The following sample reads a string and converts it to a **DateTime** type.</span></span>  
  
 <span data-ttu-id="80e6f-108">Заданы следующие входные XML-данные:</span><span class="sxs-lookup"><span data-stu-id="80e6f-108">Given the following XML input:</span></span>  
  
 <span data-ttu-id="80e6f-109">**Ввод**</span><span class="sxs-lookup"><span data-stu-id="80e6f-109">**Input**</span></span>  
  
```xml  
<Element>2001-02-27T11:13:23</Element>  
```  
  
 <span data-ttu-id="80e6f-110">Этот код преобразует строку в формат **DateTime**:</span><span class="sxs-lookup"><span data-stu-id="80e6f-110">This code converts the string to the **DateTime** format:</span></span>  
  
```vb  
reader.ReadStartElement()  
Dim vDateTime As DateTime = XmlConvert.ToDateTime(reader.ReadString())  
Console.WriteLine(vDateTime)  
```  
  
```csharp  
reader.ReadStartElement();  
DateTime vDateTime = XmlConvert.ToDateTime(reader.ReadString());  
Console.WriteLine(vDateTime);  
```  
  
## <a name="writing-strings-as-types"></a><span data-ttu-id="80e6f-111">Запись строк как типов</span><span class="sxs-lookup"><span data-stu-id="80e6f-111">Writing Strings as types</span></span>  
 <span data-ttu-id="80e6f-112">Следующий пример считывает значение типа **Int32** и преобразует его в строку.</span><span class="sxs-lookup"><span data-stu-id="80e6f-112">The following sample reads an **Int32** and converts it to a string.</span></span>  
  
 <span data-ttu-id="80e6f-113">Заданы следующие входные XML-данные:</span><span class="sxs-lookup"><span data-stu-id="80e6f-113">Given the following XML input:</span></span>  
  
 <span data-ttu-id="80e6f-114">**Ввод**</span><span class="sxs-lookup"><span data-stu-id="80e6f-114">**Input**</span></span>  
  
```xml  
<TestInt32>-2147483648</TestInt32>  
```  
  
 <span data-ttu-id="80e6f-115">Этот код преобразует данные типа **Int32** в тип **String**:</span><span class="sxs-lookup"><span data-stu-id="80e6f-115">This code converts the **Int32** into a **String**:</span></span>  
  
```vb  
Dim vInt32 As Int32 = -2147483648  
writer.WriteElementString("TestInt32", XmlConvert.ToString(vInt32))  
```  
  
```csharp  
Int32 vInt32=-2147483648;  
writer.WriteElementString("TestInt32",XmlConvert.ToString(vInt32));  
```  
  
## <a name="see-also"></a><span data-ttu-id="80e6f-116">См. также</span><span class="sxs-lookup"><span data-stu-id="80e6f-116">See Also</span></span>  
 [<span data-ttu-id="80e6f-117">Преобразование строк в типы данных .NET Framework</span><span class="sxs-lookup"><span data-stu-id="80e6f-117">Converting Strings to .NET Framework Data Types</span></span>](../../../../docs/standard/data/xml/converting-strings-to-dotnet-data-types.md)  
 [<span data-ttu-id="80e6f-118">Преобразование типов .NET Framework в строки</span><span class="sxs-lookup"><span data-stu-id="80e6f-118">Converting .NET Framework Types to Strings</span></span>](../../../../docs/standard/data/xml/converting-dotnet-types-to-strings.md)
