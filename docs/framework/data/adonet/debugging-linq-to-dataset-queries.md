---
title: "Отладка запросов в LINQ to DataSet"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f4c54015-8ce2-4c5c-8d18-7038144cc66d
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 964a4d051600621d581e05dcf6b518b2766e2750
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="debugging-linq-to-dataset-queries"></a>Отладка запросов в LINQ to DataSet
Среда [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] поддерживает отладку кода [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]. Однако существуют некоторые различия между отладкой [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] код и не-[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] управляемого кода. Большинство функций отладки работают с [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] инструкций, включая пошаговое выполнение, задание точек останова и просмотр результатов, отображаемых в окнах отладчика. Тем не менее отложенное выполнение запроса имеет некоторые побочные эффекты, которые следует учитывать при отладке [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] кода и существуют некоторые ограничения на использование, изменить и продолжить. В этом разделе обсуждаются аспекты отладки, которые являются уникальными для [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] по сравнению с отличных[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] управляемого кода.  
  
## <a name="viewing-results"></a>Просмотр результатов  
 Можно просмотреть результат [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] инструкции с помощью подсказки, окно контрольного значения и диалоговое окно «Быстрая проверка». В окне исходного текста можно остановить указатель на запросе, после чего появится элемент DataTip. Можно скопировать переменную [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] и перенести ее в окно просмотра или диалоговое окно быстрого просмотра. В [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] результат запроса вычисляется не при создании или объявлении запроса, а при его выполнении. Это называется *отложенного выполнения*. Поэтому переменная запроса не имеет значения, пока запрос не выполнен. Дополнительные сведения см. в разделе [запросов в LINQ to DataSet](../../../../docs/framework/data/adonet/queries-in-linq-to-dataset.md).  
  
 Отладчик должен выполнить запрос, чтобы отобразить его результаты. Это неявное вычисление происходит во время просмотра [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] результат запроса в отладчик и он имеет некоторые эффекты, рассмотрите возможность. Каждое вычисление запроса занимает время. Разворачивание узла результатов занимает время. В некоторых запросах повторные вычисления могу вызвать заметное снижение производительности. Вычисление запроса может также вызвать побочные эффекты, которые изменяют значение данных или состояние программы. Не все запросы имеют побочные эффекты. Чтобы определить, может ли запрос быть выполнен безопасно, без побочных эффектов, нужно понимать программный код, которым реализован запрос. Дополнительные сведения см. в разделе [побочные эффекты и выражения](http://msdn.microsoft.com/library/e1f8a6ea-9e19-481d-b6bd-df120ad3bf4e).  
  
## <a name="edit-and-continue"></a>Изменить и продолжить  
 Изменить и продолжить не поддерживает изменения в [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] запросов. Если добавление, удаление или изменение [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] инструкции во время сеанса отладки, диалоговое окно, информирующее о том, изменить и продолжить изменение не поддерживается. На этом этапе можно либо отменить изменения, либо остановить сеанс отладки и запустить новый сеанс с отредактированным кодом.  
  
 Кроме того, изменить и продолжить не поддерживает изменение типа или значения переменной, которая используется в [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] инструкции. Снова можно либо отменить изменения либо остановить и перезапустить сеанс отладки.  
  
 В Visual C# в Visual Studio, вы не может изменить и продолжить использовать на любой код в методе, содержащем [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] запроса.  
  
 В Visual Basic в Visual Studio, можно использовать изменить и продолжить в отличных[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] коде, даже в методе, содержащем [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] запроса. Можно добавить или удалить код перед [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] инструкции, даже если изменения влияют на номер строки [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] запроса. Возможности отладки Visual Basic не[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] код остается прежним, в котором он находился перед [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] был введен. Невозможно изменить, добавить или удалить [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] запроса, тем не менее, если вы не Остановите отладку, чтобы применить изменения.  
  
## <a name="see-also"></a>См. также  
 [Отладка управляемого кода](/visualstudio/debugger/debugging-managed-code)  
 [Руководство по программированию](../../../../docs/framework/data/adonet/programming-guide-linq-to-dataset.md)
