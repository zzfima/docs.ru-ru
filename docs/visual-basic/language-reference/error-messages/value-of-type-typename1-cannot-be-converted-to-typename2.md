---
title: "Значение типа &lt;имяТипа1&gt; невозможно привести к &lt;имяТипа2&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc30955"
  - "bc30955"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30955"
ms.assetid: 966b61eb-441e-48b0-bedf-ca95384ecb8b
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Значение типа &lt;имяТипа1&gt; невозможно привести к &lt;имяТипа2&gt;
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Значение типа '\<имя\_типа1\>' невозможно преобразовать в '\<имя\_типа2\>'.Несоответствие типов может быть вызвано смешиванием файловой ссылки с ссылкой проекта на сборку '\< имя\_сборки \>'.Попробуйте заменить файловую ссылку на '\<имя\_пути\>' в проекте '\<имя\_проекта1\>' на ссылку проекта '\<имя\_проекта2\>'.  
  
 В случае, когда проект делает проектную ссылку и файловую ссылку, компилятор не может гарантировать, что один тип может быть преобразован в другой.  
  
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
  
 Проект `P1` делает косвенную ссылку проекта посредством проекта `P2` на проект `P3`, а также прямую файловую ссылку на `P3`.  Объявление `commonObject` использует файловую ссылку на `P3`, в то время как при вызове `P2.getCommonClass` используется ссылка проекта на `P3`.  
  
 В этом случае проблема заключается в том, что файловая ссылка указывает путь к файлу и имя для выходного файла `P3` \(обычно p3.dll\), ссылки проекта обозначают исходный проект \(`P3`\) по имени проекта.  Таким образом, компилятор не может гарантировать, что тип `P3.commonClass` поступает из того же исходного кода через две различные ссылки.  
  
 Эта ситуация обычно возникает тогда, когда ссылка проекта и файловая ссылка смешиваются.  В предыдущем примере проблема может не возникать, если `P1` делает прямую ссылку проекта на `P3` вместо файловой ссылки.  
  
 **Идентификатор ошибки:** BC30955  
  
### Чтобы исправить эту ошибку  
  
-   Измените файловую ссылку на ссылку проекта.  
  
## См. также  
 [Преобразование типов в Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [Управление ссылками в проекте](/visual-studio/ide/managing-references-in-a-project)   
 [Практическое руководство. Добавление и удаление ссылок с помощью диалогового окна "Добавление ссылок"](http://msdn.microsoft.com/ru-ru/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)