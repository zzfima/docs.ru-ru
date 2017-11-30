---
title: "Непредвиденная ошибка, так как операционная система не может получить ресурсы, требуемые для запуска одного экземпляра."
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrAppModel_CantGetMemoryMappedFile
ms.assetid: 0d9f2a30-ff72-4355-8060-744f22339359
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8969303d66e946d5579c6cca592b5701c4ebd632
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
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
 [Страница "Приложение" в конструкторе проектов (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)  
 [Основы отладки](/visualstudio/debugger/debugger-basics)  
 [Обращайтесь к нам](/visualstudio/ide/talk-to-us)
