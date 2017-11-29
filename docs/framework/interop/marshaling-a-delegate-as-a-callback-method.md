---
title: "Маршалинг делегата как метода обратного вызова"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data marshaling, Callback sample
- marshaling, Callback sample
ms.assetid: 6ddd7866-9804-4571-84de-83f5cc017a5a
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c8c4eca35c406b38da603dc10358920ee887b137
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="marshaling-a-delegate-as-a-callback-method"></a>Маршалинг делегата как метода обратного вызова
В этом примере показан способ передачи делегатов в неуправляемую функцию, ожидающую указатели на функции. Делегат — это класс, который может содержать ссылку на метод. Делегат эквивалентен типобезопасному указателю на функцию или функции обратного вызова.  
  
> [!NOTE]
>  При использовании делегата в вызове функции общеязыковая среда выполнения защищает делегат от сборщика мусора в течение этого вызова. Однако если неуправляемая функция сохраняет делегат для использования после завершения вызова, необходимо вручную запретить сбор мусора до того, как неуправляемая функция завершит обработку делегата. Дополнительные сведения см. в разделах [Пример HandleRef](http://msdn.microsoft.com/en-us/ab23b04e-1d53-4ec7-b27a-e892d9298959) и [Пример GCHandle](http://msdn.microsoft.com/en-us/6acce798-0385-4ded-a790-77da842c113f).  
  
 В примере обратного вызова используются следующие неуправляемые функции со своими первоначальными объявлениями:  
  
-   функция **TestCallBack**, экспортированная из PinvokeLib.dll;  
  
    ```  
    void TestCallBack(FPTR pf, int value);  
    ```  
  
-   функция **TestCallBack2**, экспортированная из PinvokeLib.dll.  
  
    ```  
    void TestCallBack2(FPTR2 pf2, char* value);  
    ```  
  
 [PinvokeLib.dll](http://msdn.microsoft.com/en-us/5d1438d7-9946-489d-8ede-6c694a08f614) — это пользовательская неуправляемая библиотека, содержащая реализацию вышеуказанных функций.  
  
 В этом примере класс `LibWrap` содержит управляемые прототипы методов `TestCallBack` и `TestCallBack2`. Оба метода передают делегат функции обратного вызова в качестве параметра. Сигнатура делегата должна соответствовать сигнатуре метода, на который ссылается делегат. Например, подписи делегатов для `FPtr` и `FPtr2` аналогичны методам `DoSomething` и `DoSomething2`.  
  
## <a name="declaring-prototypes"></a>Объявление прототипов  
 [!code-cpp[Conceptual.Interop.Marshaling#37](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/callback.cpp#37)]
 [!code-csharp[Conceptual.Interop.Marshaling#37](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/callback.cs#37)]
 [!code-vb[Conceptual.Interop.Marshaling#37](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/callback.vb#37)]  
  
## <a name="calling-functions"></a>Вызов функций  
 [!code-cpp[Conceptual.Interop.Marshaling#38](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/callback.cpp#38)]
 [!code-csharp[Conceptual.Interop.Marshaling#38](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/callback.cs#38)]
 [!code-vb[Conceptual.Interop.Marshaling#38](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/callback.vb#38)]  
  
## <a name="see-also"></a>См. также  
 [Различные примеры маршалинга](http://msdn.microsoft.com/en-us/a915c948-54e9-4d0f-a525-95a77fd8ed70)  
 [Типы данных вызовов неуправляемого кода](http://msdn.microsoft.com/en-us/16014d9f-d6bd-481e-83f0-df11377c550f)  
 [Создание прототипов в управляемом коде](../../../docs/framework/interop/creating-prototypes-in-managed-code.md)
