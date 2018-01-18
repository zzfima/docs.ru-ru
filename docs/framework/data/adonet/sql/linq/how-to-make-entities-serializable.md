---
title: "Практическое руководство. Обеспечение сериализуемости сущностей"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a6c5bf6e-064a-4f77-b74c-76b3a5dec309
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 8f6121b8548c1909f4680419a1fee8f9848ebc1d
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-make-entities-serializable"></a><span data-ttu-id="1b584-102">Практическое руководство. Обеспечение сериализуемости сущностей</span><span class="sxs-lookup"><span data-stu-id="1b584-102">How to: Make Entities Serializable</span></span>
<span data-ttu-id="1b584-103">Возможность сериализации сущностей можно обеспечить при создании кода.</span><span class="sxs-lookup"><span data-stu-id="1b584-103">You can make entities serializable when you generate your code.</span></span> <span data-ttu-id="1b584-104">К классам сущностей добавляется атрибут <xref:System.Runtime.Serialization.DataContractAttribute>, а к столбцам - атрибут <xref:System.Runtime.Serialization.DataMemberAttribute>.</span><span class="sxs-lookup"><span data-stu-id="1b584-104">Entity classes are decorated with the <xref:System.Runtime.Serialization.DataContractAttribute> attribute, and columns with the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute.</span></span>  
  
 <span data-ttu-id="1b584-105">Для этой цели пользователи среды [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] могут воспользоваться конструктором [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1b584-105">Developers using [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] for this purpose.</span></span>  
  
 <span data-ttu-id="1b584-106">При использовании средства командной строки SQLMetal, использовать **/serialization** вариант с `unidirectional` аргумент.</span><span class="sxs-lookup"><span data-stu-id="1b584-106">If you are using the SQLMetal command-line tool, use the **/serialization** option with the `unidirectional` argument.</span></span> <span data-ttu-id="1b584-107">Дополнительные сведения см. в разделе [SQLMetal.exe (средство создания кода)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span><span class="sxs-lookup"><span data-stu-id="1b584-107">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1b584-108">Пример</span><span class="sxs-lookup"><span data-stu-id="1b584-108">Example</span></span>  
 <span data-ttu-id="1b584-109">В следующих командах средства командной строки SQLMetal создают файлы, содержащие сериализуемые сущности.</span><span class="sxs-lookup"><span data-stu-id="1b584-109">The following SQLMetal command lines produce files that have serializable entities.</span></span>  
  
```  
sqlmetal /code:nwserializable.vb /language:vb "c:\northwnd.mdf" /sprocs /functions /pluralize /serialization:unidirectional  
```  
  
```  
sqlmetal /code:nwserializable.cs /language:csharp "c:\northwnd.mdf" /sprocs /functions /pluralize /serialization:unidirectional  
```  
  
## <a name="see-also"></a><span data-ttu-id="1b584-110">См. также</span><span class="sxs-lookup"><span data-stu-id="1b584-110">See Also</span></span>  
 [<span data-ttu-id="1b584-111">Сериализация</span><span class="sxs-lookup"><span data-stu-id="1b584-111">Serialization</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/serialization.md)  
 [<span data-ttu-id="1b584-112">Создание модели объектов</span><span class="sxs-lookup"><span data-stu-id="1b584-112">Creating the Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)
