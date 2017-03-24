---
title: "Это приложение с одним экземпляром не удалось подключиться к исходному экземпляру | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrAppModel_SingleInstanceCantConnect
ms.assetid: 7c2c0cee-02a1-4157-be03-39d18e18408f
caps.latest.revision: 12
author: stevehoag
ms.author: shoag
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 17a3ecd69e0e0974b2a8fc50090097b93dc0def3
ms.lasthandoff: 03/13/2017

---
# <a name="this-single-instance-application-could-not-connect-to-the-original-instance"></a>Данное приложение, допускающее только один экземпляр, не может подключиться к первоначальному экземпляру
Данное приложение, допускающее только один экземпляр, не может подключиться к первоначальному экземпляру. Вот некоторые возможные причины этой проблемы.  
  
-   Исходный экземпляр перестал отвечать.  
  
-   Приложение не имеет разрешений на создание объектов ядра. Дополнительные сведения об объектах ядра см. в разделе [мьютексы](http://msdn.microsoft.com/library/9dd06e25-12c0-4a9e-855a-452dc83803e2).  
  
     Базовое имя для объектов ядра получается из последовательного объединения GUID сборки, основного номера версии и дополнительного номера версии. Например, базовое имя может быть `3639f15d-9547-43da-8145-60da347829915.1`.  
  
## <a name="to-correct-this-error-when-developing-the-application"></a>Исправление этой ошибки при разработке приложения  
  
1.  Проверьте, не переходит ли приложение в состояние, в котором оно не отвечает на запросы.  
  
2.  Убедитесь в том, что приложение имеет достаточно разрешений на создание объектов ядра.  
  
3.  Перезапустите исходный экземпляр приложения.  
  
4.  Перезагрузите компьютер, чтобы удалить все процессы, которые могут использовать ресурсы, необходимые приложению для подключения к исходному экземпляру.  
  
5.  Задокументируйте обстоятельства возникновения ошибки и обратитесь в службу технической поддержки Майкрософт.  
  
## <a name="see-also"></a>См. также  
 [NIB: Как: Укажите поведение создания экземпляров приложения (Visual Basic)](http://msdn.microsoft.com/en-us/48539ad8-d960-4210-beab-ee65f6c6dc6e)   
 [Основы отладчика](https://docs.microsoft.com/visualstudio/debugger/debugger-basics)   
 [PAVEOVER поддержка и продукта специальные возможности](http://msdn.microsoft.com/en-us/14e1d293-7b6d-40a6-bf3e-a92f8ee6c88c)
