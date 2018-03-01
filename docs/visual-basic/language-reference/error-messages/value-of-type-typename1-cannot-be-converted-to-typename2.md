---
title: "Значение типа &#39; &lt;Имя_типа1&gt;&#39; невозможно преобразовать в &#39;&lt; имя_типа2&gt;&#39;"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30955
- bc30955
helpviewer_keywords:
- BC30955
ms.assetid: 966b61eb-441e-48b0-bedf-ca95384ecb8b
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b583c4272dd6e964de99fb14d2795152c655f3aa
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="value-of-type-39lttypename1gt39-cannot-be-converted-to-39lttypename2gt39"></a>Значение типа &#39; &lt;Имя_типа1&gt;&#39; невозможно преобразовать в &#39;&lt; имя_типа2&gt;&#39;
Значение типа "\<Имя_типа1 >" нельзя преобразовать в "\<имя_типа2 >". Несоответствие типов может быть вызвана смешением ссылки на файл со ссылкой из проекта на сборку "\<имя_сборки >". Попробуйте заменить ссылку на файл "\<filepath >" в проекте "\<имя_проекта1 >" со ссылкой проекта "\<имя_проекта2 >".  
  
 В случае, когда проект делает ссылку на проект и ссылку на файл компилятор не гарантирует, что одного типа могут преобразовываться в другой.  
  
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
  
 В этой ситуации проблема в том, что ссылка на файл задает путь к файлу и имя выходного файла `P3` (обычно p3.dll), а ссылки проекта обозначают исходный проект (`P3`) по имени проекта. По этой причине компилятор не может гарантировать, что тип `P3.commonClass` поступают из того же исходного кода через две различные ссылки.  
  
 Такая ситуация обычно возникает, когда ссылка проекта и ссылки на файлы со смешанными. На предыдущем рисунке, проблема не возникнет, если `P1` сделать ссылку на проект прямой `P3` вместо ссылки на файл.  
  
 **Идентификатор ошибки:** BC30955  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Измените ссылку на файл для ссылки на проект.  
  
## <a name="see-also"></a>См. также  
 [Преобразования типов в Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [Управление ссылками в проекте](/visualstudio/ide/managing-references-in-a-project)  
 
