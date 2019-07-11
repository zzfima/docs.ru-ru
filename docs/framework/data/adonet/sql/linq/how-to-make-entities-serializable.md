---
title: Практическое руководство. Как обеспечить сериализации сущностей
ms.date: 03/30/2017
ms.assetid: a6c5bf6e-064a-4f77-b74c-76b3a5dec309
ms.openlocfilehash: fd687ba5dce16baee063f1d3bb9521c6664988b0
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67743288"
---
# <a name="how-to-make-entities-serializable"></a>Практическое руководство. Как обеспечить сериализации сущностей
Возможность сериализации сущностей можно обеспечить при создании кода. К классам сущностей добавляется атрибут <xref:System.Runtime.Serialization.DataContractAttribute>, а к столбцам - атрибут <xref:System.Runtime.Serialization.DataMemberAttribute>.  
  
 Разработчики, использующие Visual Studio можно использовать реляционный конструктор объектов для этой цели.  
  
 Если вы используете средство командной строки SQLMetal, использовать **/serialization** с параметром `unidirectional` аргумент. Дополнительные сведения см. в разделе [SQLMetal.exe (средство создания кода)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).  
  
## <a name="example"></a>Пример  
 В следующих командах средства командной строки SQLMetal создают файлы, содержащие сериализуемые сущности.  
  
```  
sqlmetal /code:nwserializable.vb /language:vb "c:\northwnd.mdf" /sprocs /functions /pluralize /serialization:unidirectional  
```  
  
```  
sqlmetal /code:nwserializable.cs /language:csharp "c:\northwnd.mdf" /sprocs /functions /pluralize /serialization:unidirectional  
```  
  
## <a name="see-also"></a>См. также

- [Сериализация](../../../../../../docs/framework/data/adonet/sql/linq/serialization.md)
- [Создание модели объектов](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)
