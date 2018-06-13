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
# <a name="how-to-make-entities-serializable"></a>Практическое руководство. Обеспечение сериализуемости сущностей
Возможность сериализации сущностей можно обеспечить при создании кода. К классам сущностей добавляется атрибут <xref:System.Runtime.Serialization.DataContractAttribute>, а к столбцам - атрибут <xref:System.Runtime.Serialization.DataMemberAttribute>.  
  
 С помощью Visual Studio разработчики могут использовать [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] для этой цели.  
  
 При использовании средства командной строки SQLMetal, использовать **/serialization** вариант с `unidirectional` аргумент. Дополнительные сведения см. в разделе [SQLMetal.exe (средство создания кода)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).  
  
## <a name="example"></a>Пример  
 В следующих командах средства командной строки SQLMetal создают файлы, содержащие сериализуемые сущности.  
  
```  
sqlmetal /code:nwserializable.vb /language:vb "c:\northwnd.mdf" /sprocs /functions /pluralize /serialization:unidirectional  
```  
  
```  
sqlmetal /code:nwserializable.cs /language:csharp "c:\northwnd.mdf" /sprocs /functions /pluralize /serialization:unidirectional  
```  
  
## <a name="see-also"></a>См. также  
 [Сериализация](../../../../../../docs/framework/data/adonet/sql/linq/serialization.md)  
 [Создание модели объектов](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)
