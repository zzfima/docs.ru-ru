---
title: Ссылка <reference> на дружественную сборку является недопустимой
ms.date: 07/20/2015
f1_keywords:
- vbc31535
- bc31535
helpviewer_keywords:
- BC31535
ms.assetid: 6540c1d0-bb19-4051-a579-2e4f9094585e
ms.openlocfilehash: ff2cdbebe13f6224209ef8da62600c99348c911b
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55286823"
---
# <a name="friend-assembly-reference-reference-is-invalid"></a>Ссылка на дружественную сборку \<ссылку > является недопустимым
Ссылка на дружественную сборку \<ссылку > является недопустимым. Для сборок, подписанных строгим именем, в объявлении InternalsVisibleTo должен быть указан открытый ключ.  
  
 Имя сборки, передаваемое <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> конструктор атрибута идентифицирует сборку со строгим именем, но он не включает `PublicKey` атрибута.  
  
 **Идентификатор ошибки:** BC31535  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Определите открытый ключ для строгое имя дружественной сборки. Поместить открытый ключ как часть имени сборки, передаваемый в <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> конструктор атрибута с помощью `PublicKey` атрибута.  
  
## <a name="see-also"></a>См. также
- <xref:System.Reflection.AssemblyName>
- [Дружественные сборки](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md)


