---
title: "По умолчанию свойство &quot;&lt;propertyname1&gt;«конфликтует со свойством по умолчанию»&lt;propertyname2&gt;«in»&lt;classname&gt;&quot; и должен быть объявлен как &quot;Shadows&quot; | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc40007
- bc40007
dev_langs:
- VB
helpviewer_keywords:
- BC40007
ms.assetid: 692ccf76-5715-4f11-a972-84cf9de30bc1
caps.latest.revision: 9
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 803b42b7659c16fd97251635e4b6ba49362e0a02
ms.lasthandoff: 03/13/2017

---
# <a name="default-property-39ltpropertyname1gt39-conflicts-with-default-property-39ltpropertyname2gt39-in-39ltclassnamegt39-and-so-should-be-declared-39shadows39"></a>По умолчанию свойство "&lt;propertyname1&gt;«конфликтует со свойством по умолчанию»&lt;propertyname2&gt;«in»&lt;classname&gt;" и должен быть объявлен как 'Shadows'
Свойство объявлено с тем же именем, как свойства, определенные в базовом классе. В этом случае свойство в данном классе должно скрывать свойство базового класса.  
  
 Это сообщение является предупреждением. `Shadows`подразумевается по умолчанию. Дополнительные сведения о скрытии предупреждений или обработке предупреждений как ошибок см. в разделе [в Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Идентификатор ошибки:** BC40007  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Добавление `Shadows` объявляемого ключевое слово объявление или измените имя свойства.  
  
## <a name="see-also"></a>См. также  
 [Тени](../../../visual-basic/language-reference/modifiers/shadows.md)   
 [Сокрытие в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
