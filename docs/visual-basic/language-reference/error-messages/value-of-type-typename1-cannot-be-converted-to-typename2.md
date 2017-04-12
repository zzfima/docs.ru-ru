---
title: "Значение типа &quot;&lt;typename1&gt;«невозможно преобразовать»&lt;typename2&gt;&quot; | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30955
- bc30955
dev_langs:
- VB
helpviewer_keywords:
- BC30955
ms.assetid: 966b61eb-441e-48b0-bedf-ca95384ecb8b
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
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
ms.openlocfilehash: c973d5e2aa03d423e1dea8053946172655f08490
ms.lasthandoff: 03/13/2017

---
# <a name="value-of-type-39lttypename1gt39-cannot-be-converted-to-39lttypename2gt39"></a>Значение типа "&lt;typename1&gt;«невозможно преобразовать»&lt;typename2&gt;"
Значение типа "\<typename1 настроек" нельзя преобразовать в "\<typename2 настроек". Несоответствие типов может быть вызвана смешением ссылки на файл со ссылкой из проекта на сборку "\<assemblyname настроек". Попробуйте заменить ссылку на файл "\<filepath настроек" в проекте "\<projectname1 настроек" со ссылкой на проект "\<projectname2 настроек".  
  
 В ситуации, когда проект делает ссылку на проект и ссылки на файл компилятор не может гарантировать, что один тип можно преобразовать в другой.  
  
 Следующий псевдокод иллюстрирует ситуацию, которая может вызвать эту ошибку.  
  
 `' ================ Visual Basic project P1 ================`  
  
 `'        P1 makes a PROJECT REFERENCE to project P2`  
  
 `'        and a FILE REFERENCE to project P3.`  
  
 `Public commonObject As P3.commonClass`  
  
 `commonObject = P2.getCommonClass()`  
  
 `' ================ Visual Basic project P2 ================`  
  
 `'        P2 makes a PROJECT REFERENCE to project P3`  
  
 `Public Function getCommonClass() As P3.commonClass`  
  
 `Return New P3.commonClass`  
  
 `End Function`  
  
 `' ================ Visual Basic project P3 ================`  
  
 `Public Class commonClass`  
  
 `End Class`  
  
 Проект `P1` делает косвенную ссылку проекта посредством проекта `P2` проект `P3`, а также прямые ссылки на файл `P3`. Объявление `commonObject` использует ссылку на файл `P3`, тогда как вызов `P2.getCommonClass` использует ссылку на проект `P3`.  
  
 В этом случае проблема: ссылка на файл задает путь и имя файла для выходного файла `P3` (обычно p3.dll), а в ссылки проекта обозначают исходный проект (`P3`) по имени проекта. По этой причине компилятор не может гарантировать, что тип `P3.commonClass` поступает из того же исходного кода через две различные ссылки.  
  
 Это обычно происходит, когда ссылка проекта и файловая ссылка смешиваются. В предыдущем примере проблема может не возникать при `P1` сделать прямую ссылку проекта на `P3` вместо ссылки на файл.  
  
 **Идентификатор ошибки:** BC30955  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Измените ссылку на файл ссылку на проект.  
  
## <a name="see-also"></a>См. также  
 [Преобразования типов в Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [Управление ссылками проекта](https://docs.microsoft.com/visualstudio/ide/managing-references-in-a-project)   
 [NIB. Практическое руководство. Добавление и удаление ссылок с помощью диалогового окна "Добавление ссылки"](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)
