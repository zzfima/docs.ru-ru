---
title: "Значение типа &quot;&lt;typename1&gt;«невозможно преобразовать»&lt;typename2&gt;&quot; (множественные ссылки на файл) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30961
- bc30961
dev_langs:
- VB
helpviewer_keywords:
- BC30961
ms.assetid: 8be5aa0d-d236-4ac3-aa9c-5044f9f6562b
caps.latest.revision: 9
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
ms.openlocfilehash: 732291ce9c4b83bb9fc7e83fbbc2a8da9748db59
ms.lasthandoff: 03/13/2017

---
# <a name="value-of-type-39lttypename1gt39-cannot-be-converted-to-39lttypename2gt39-multiple-file-references"></a>Значение типа "&lt;typename1&gt;«невозможно преобразовать»&lt;typename2&gt;" (множественные ссылки на файл)
Значение типа "\<typename1 настроек" нельзя преобразовать в "\<typename2 настроек". Несоответствие типов может быть вызвана смешением ссылки на файл "\<filepath1 настроек" в проекте "\<projectname1 настроек" со ссылкой на файл "\<filepath2 настроек" в проекте "\<projectname2 настроек". Если обе сборки идентичны, попробуйте заменить эти ссылки так, чтобы они ссылались из одного места.  
  
 В ситуации, когда проект делает более одной ссылки на сборку компилятор не может гарантировать, что один тип можно преобразовать в другой.  
  
 Каждая ссылка на файл задает путь и имя файла для выходного файла проекта (как правило, файл DLL). Компилятор не может гарантировать, что выходные файлы будут взяты из одного источника, либо что они представляют та же версия той же сборки. Таким образом он не может гарантировать, что типы в различных ссылках относятся к одному типу, или даже что один можно преобразовать в другой.  
  
 Если вы знаете, что указанные сборки имеют одинаковый идентификатор сборки можно использовать ссылку на один файл. *Удостоверение сборки* включает имя сборки, версию, открытый ключ (при его наличии), язык и региональные параметры. Эти сведения уникально идентифицируют сборку.  
  
 **Идентификатор ошибки:** BC30961  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Если указанные сборки имеют одинаковый идентификатор сборки, затем удалите или замените одну из ссылок на файл таким образом, что только одна ссылка на файл.  
  
-   Если указанные сборки не имеют одинаковый идентификатор сборки, измените код, чтобы он пытался выполнить преобразование одного типа в другой.  
  
## <a name="see-also"></a>См. также  
 [Преобразования типов в Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [Управление ссылками проекта](https://docs.microsoft.com/visualstudio/ide/managing-references-in-a-project)   
 [NIB. Практическое руководство. Добавление и удаление ссылок с помощью диалогового окна "Добавление ссылки"](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)
