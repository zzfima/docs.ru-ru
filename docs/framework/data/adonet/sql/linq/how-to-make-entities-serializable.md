---
title: Практическое руководство. Обеспечение сериализуемости сущностей
ms.date: 03/30/2017
ms.assetid: a6c5bf6e-064a-4f77-b74c-76b3a5dec309
ms.openlocfilehash: c3b877df9707e0f98dbc2238d910842649def07f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33354950"
---
# <a name="how-to-make-entities-serializable"></a><span data-ttu-id="190ee-102">Практическое руководство. Обеспечение сериализуемости сущностей</span><span class="sxs-lookup"><span data-stu-id="190ee-102">How to: Make Entities Serializable</span></span>
<span data-ttu-id="190ee-103">Возможность сериализации сущностей можно обеспечить при создании кода.</span><span class="sxs-lookup"><span data-stu-id="190ee-103">You can make entities serializable when you generate your code.</span></span> <span data-ttu-id="190ee-104">К классам сущностей добавляется атрибут <xref:System.Runtime.Serialization.DataContractAttribute>, а к столбцам - атрибут <xref:System.Runtime.Serialization.DataMemberAttribute>.</span><span class="sxs-lookup"><span data-stu-id="190ee-104">Entity classes are decorated with the <xref:System.Runtime.Serialization.DataContractAttribute> attribute, and columns with the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute.</span></span>  
  
 <span data-ttu-id="190ee-105">С помощью Visual Studio разработчики могут использовать [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] для этой цели.</span><span class="sxs-lookup"><span data-stu-id="190ee-105">Developers using Visual Studio can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] for this purpose.</span></span>  
  
 <span data-ttu-id="190ee-106">При использовании средства командной строки SQLMetal, использовать **/serialization** вариант с `unidirectional` аргумент.</span><span class="sxs-lookup"><span data-stu-id="190ee-106">If you are using the SQLMetal command-line tool, use the **/serialization** option with the `unidirectional` argument.</span></span> <span data-ttu-id="190ee-107">Дополнительные сведения см. в разделе [SQLMetal.exe (средство создания кода)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span><span class="sxs-lookup"><span data-stu-id="190ee-107">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="190ee-108">Пример</span><span class="sxs-lookup"><span data-stu-id="190ee-108">Example</span></span>  
 <span data-ttu-id="190ee-109">В следующих командах средства командной строки SQLMetal создают файлы, содержащие сериализуемые сущности.</span><span class="sxs-lookup"><span data-stu-id="190ee-109">The following SQLMetal command lines produce files that have serializable entities.</span></span>  
  
```  
sqlmetal /code:nwserializable.vb /language:vb "c:\northwnd.mdf" /sprocs /functions /pluralize /serialization:unidirectional  
```  
  
```  
sqlmetal /code:nwserializable.cs /language:csharp "c:\northwnd.mdf" /sprocs /functions /pluralize /serialization:unidirectional  
```  
  
## <a name="see-also"></a><span data-ttu-id="190ee-110">См. также</span><span class="sxs-lookup"><span data-stu-id="190ee-110">See Also</span></span>  
 [<span data-ttu-id="190ee-111">Сериализация</span><span class="sxs-lookup"><span data-stu-id="190ee-111">Serialization</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/serialization.md)  
 [<span data-ttu-id="190ee-112">Создание модели объектов</span><span class="sxs-lookup"><span data-stu-id="190ee-112">Creating the Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)
