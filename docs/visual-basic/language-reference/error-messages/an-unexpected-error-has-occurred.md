---
title: "Непредвиденная ошибка, так как ресурс операционной системы, необходимые для запуска одного экземпляра не может быть получена | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrAppModel_CantGetMemoryMappedFile
dev_langs:
- VB
ms.assetid: 0d9f2a30-ff72-4355-8060-744f22339359
caps.latest.revision: 10
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
ms.openlocfilehash: 44432a2c393abb01141d09cf5f28c6fd29c5bc43
ms.lasthandoff: 03/13/2017

---
# <a name="an-unexpected-error-has-occurred-because-an-operating-system-resource-required-for-single-instance-startup-cannot-be-acquired"></a>Непредвиденная ошибка, так как операционная система не может получить ресурсы, требуемые для запуска одного экземпляра.
Приложению не удалось получить требуемый ресурс операционной системы. Вот некоторые возможные причины этой проблемы.  
  
-   Приложение не имеет разрешений на создание именованных объектов операционной системы.  
  
-   Среда CLR не имеет разрешений на создание размещенных в памяти файлов.  
  
-   Приложению требуется доступ к объекту операционной системы, который используется другим процессом.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Убедитесь, что у приложения достаточно прав на создание именованных объектов операционной системы.  
  
2.  Убедитесь, что у среды CLR достаточно прав на создание размещенных в памяти файлов.  
  
3.  Перезапустите компьютер, чтобы очистить все процессы, которые могут использовать ресурс, необходимый для подключения к приложению исходного экземпляра.  
  
4.  Запомните, при каких условиях произошла ошибка, и обратитесь в службу технической поддержки Майкрософт.  
  
## <a name="see-also"></a>См. также  
 [Страница "Приложение" в конструкторе проектов (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/application-page-project-designer-visual-basic)   
 [Основы отладчика](https://docs.microsoft.com/visualstudio/debugger/debugger-basics)   
 [Обращайтесь к нам](https://docs.microsoft.com/visualstudio/ide/talk-to-us)
