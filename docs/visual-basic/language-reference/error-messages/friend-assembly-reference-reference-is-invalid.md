---
title: "Ссылка на дружественную сборку &lt;ссылка&gt; является недопустимым"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc31535
- bc31535
helpviewer_keywords: BC31535
ms.assetid: 6540c1d0-bb19-4051-a579-2e4f9094585e
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 39ae94e309ee8d18e6b5317445b7e4b7f6a42af9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="friend-assembly-reference-ltreferencegt-is-invalid"></a>Ссылка на дружественную сборку &lt;ссылка&gt; является недопустимым
Ссылка на дружественную сборку \<ссылка > является недопустимым. Для сборок, подписанных строгим именем, в объявлении InternalsVisibleTo должен быть указан открытый ключ.  
  
 Имя сборки, передаваемое <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> конструктор атрибута идентифицирует сборку строгим именем, но не включает `PublicKey` атрибута.  
  
 **Идентификатор ошибки:** BC31535  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Определите открытый ключ для сборки со строгими именами friend. Поместить открытый ключ как часть имени сборки, передаваемый в <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> конструктор атрибута с помощью `PublicKey` атрибута.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Reflection.AssemblyName>  
 [Дружественные сборки](http://msdn.microsoft.com/library/df0c70ea-2c2a-4bdc-9526-df951ad2d055)  
 [Практическое руководство. Создание подписанных дружественных сборок](http://msdn.microsoft.com/library/f5542300-58b4-4e1c-b809-8df11e95e69b)
