---
title: Ссылка <reference> на дружественную сборку является недопустимой
ms.date: 07/20/2015
f1_keywords:
- vbc31535
- bc31535
helpviewer_keywords:
- BC31535
ms.assetid: 6540c1d0-bb19-4051-a579-2e4f9094585e
ms.openlocfilehash: 796c16e912283d86496a4ccbd3b675ac1433f02d
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57356407"
---
# <a name="friend-assembly-reference-reference-is-invalid"></a>Ссылка на дружественную сборку \<ссылку > является недопустимым
Ссылка на дружественную сборку \<ссылку > является недопустимым. Для сборок, подписанных строгим именем, в объявлении InternalsVisibleTo должен быть указан открытый ключ.  
  
 Имя сборки, передаваемое <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> конструктор атрибута идентифицирует сборку со строгим именем, но он не включает `PublicKey` атрибута.  
  
 **Идентификатор ошибки:** BC31535  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Определите открытый ключ для строгое имя дружественной сборки. Поместить открытый ключ как часть имени сборки, передаваемый в <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> конструктор атрибута с помощью `PublicKey` атрибута.  
  
## <a name="see-also"></a>См. также
- <xref:System.Reflection.AssemblyName>
- [Дружественные сборки](../../../standard/assembly/friend-assemblies.md)


