---
title: Практическое руководство. Как обеспечить сериализации сущностей
ms.date: 03/30/2017
ms.assetid: a6c5bf6e-064a-4f77-b74c-76b3a5dec309
ms.openlocfilehash: 5e9d078ed2daacfa48b09693f533e9aade613281
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72002711"
---
# <a name="how-to-make-entities-serializable"></a><span data-ttu-id="71d18-102">Практическое руководство. Как обеспечить сериализации сущностей</span><span class="sxs-lookup"><span data-stu-id="71d18-102">How to: Make Entities Serializable</span></span>
<span data-ttu-id="71d18-103">Возможность сериализации сущностей можно обеспечить при создании кода.</span><span class="sxs-lookup"><span data-stu-id="71d18-103">You can make entities serializable when you generate your code.</span></span> <span data-ttu-id="71d18-104">К классам сущностей добавляется атрибут <xref:System.Runtime.Serialization.DataContractAttribute>, а к столбцам - атрибут <xref:System.Runtime.Serialization.DataMemberAttribute>.</span><span class="sxs-lookup"><span data-stu-id="71d18-104">Entity classes are decorated with the <xref:System.Runtime.Serialization.DataContractAttribute> attribute, and columns with the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute.</span></span>  
  
 <span data-ttu-id="71d18-105">Разработчики, использующие Visual Studio, могут использовать реляционный конструктор объектов для этой цели.</span><span class="sxs-lookup"><span data-stu-id="71d18-105">Developers using Visual Studio can use the Object Relational Designer for this purpose.</span></span>  
  
 <span data-ttu-id="71d18-106">При использовании программы командной строки SQLMetal используйте параметр **/Serialization** с аргументом `unidirectional`.</span><span class="sxs-lookup"><span data-stu-id="71d18-106">If you are using the SQLMetal command-line tool, use the **/serialization** option with the `unidirectional` argument.</span></span> <span data-ttu-id="71d18-107">Дополнительные сведения см. в разделе [SQLMetal.exe (средство создания кода)](../../../../tools/sqlmetal-exe-code-generation-tool.md).</span><span class="sxs-lookup"><span data-stu-id="71d18-107">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="71d18-108">Пример</span><span class="sxs-lookup"><span data-stu-id="71d18-108">Example</span></span>  
 <span data-ttu-id="71d18-109">В следующих командах средства командной строки SQLMetal создают файлы, содержащие сериализуемые сущности.</span><span class="sxs-lookup"><span data-stu-id="71d18-109">The following SQLMetal command lines produce files that have serializable entities.</span></span>  
  
```console  
sqlmetal /code:nwserializable.vb /language:vb "c:\northwnd.mdf" /sprocs /functions /pluralize /serialization:unidirectional  
```  
  
```console  
sqlmetal /code:nwserializable.cs /language:csharp "c:\northwnd.mdf" /sprocs /functions /pluralize /serialization:unidirectional  
```  
  
## <a name="see-also"></a><span data-ttu-id="71d18-110">См. также</span><span class="sxs-lookup"><span data-stu-id="71d18-110">See also</span></span>

- [<span data-ttu-id="71d18-111">Сериализация</span><span class="sxs-lookup"><span data-stu-id="71d18-111">Serialization</span></span>](serialization.md)
- [<span data-ttu-id="71d18-112">Создание модели объектов</span><span class="sxs-lookup"><span data-stu-id="71d18-112">Creating the Object Model</span></span>](creating-the-object-model.md)
