---
title: "Оператор End | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.End"
  - "End"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "код, выход"
  - "End - ключевое слово, End - операторы"
  - "End - оператор"
  - "выполнение, завершение"
  - "выполнение, остановка"
  - "файлы, закрытие"
  - "завершение программы"
  - "программы, выход"
ms.assetid: 0e64467c-0f34-4aab-9ddd-43f8b9d55d90
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# Оператор End
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Немедленно прекращает выполнение.  
  
## Синтаксис  
  
```  
End  
```  
  
## Заметки  
 Оператор `End` можно поместить любое место в процедуре, чтобы заставить все приложение остановиться.  `End` закрывает все файлы, открытые оператором `Open` и очищает все переменные приложения.  Приложение закрывается, как только не останется других программ, поддерживающих ссылки на его объекты, и код программы не будет выполняться.  
  
> [!NOTE]
>  Оператор `End` резко останавливает выполнение кода, и не вызывает метод `Dispose` или `Finalize`, или любой другой код Visual Basic.  Ссылки на объекты, хранящиеся в других программах, становятся недействительными.  Если оператор `End` оказывается внутри блока `Try` или `Catch`, управление не передается в соответствующий блок `Finally`.  
  
 Оператор `Stop` приостанавливает выполнение, однако, в отличие от `End`, не закрывает файлы и не очищает переменные, если только не встречается в скомпилированном исполняемом файле \(с расширением EXE\).  
  
 Поскольку оператор `End` завершает приложение, не обращая внимания на какие\-либо ресурсы, которые могут быть открыты, следует попробовать аккуратно закрыть их перед его использованием.  Например, если в приложении имеются открытые формы, их следует закрыть перед передачей управления оператору `End`.  
  
 Не следует часто применять оператор `End`, только когда требуется немедленно прекратить выполнение приложения.  Обычные способы завершения процедуры \([Оператор Return](../../../visual-basic/language-reference/statements/return-statement.md) и [Оператор Exit](../../../visual-basic/language-reference/statements/exit-statement.md)\) не только аккуратно завершают процедуру, но также дают вызывающему коду возможность безопасного закрытия приложения.  Для консольного приложения, например, можно просто использовать `Return` из процедуры `Main`.  
  
> [!IMPORTANT]
>  Оператор `End` вызывает метод <xref:System.Environment.Exit%2A> класса <xref:System.Environment> в пространстве имен <xref:System>.  <xref:System.Environment.Exit%2A> требует иметь разрешение `UnmanagedCode`.  Иначе создается исключение <xref:System.Security.SecurityException>.  
  
 Если после [Оператор End \<ключевое\_слово\>](../../../visual-basic/language-reference/statements/end-keyword-statement.md) указано ключевое слово, это означает конец определения соответствующей процедуры или блока.  Например, `End Function` завершает определение процедуры `Function`.  
  
## Пример  
 В приведенном ниже примере оператор `End` используется для завершения выполнения кода по требованию пользователя.  
  
 [!code-vb[VbVersHelp60Controls#64](../../../visual-basic/language-reference/statements/codesnippet/visualbasic/VbVersHelp60Controls/Form1.vb#64)]  
  
## Примечания для разработчиков приложений смарт\-устройств  
 Этот оператор не поддерживается.  
  
## См. также  
 <xref:System.Security.Permissions.SecurityPermissionFlag>   
 [Оператор Stop](../../../visual-basic/language-reference/statements/stop-statement.md)   
 [Оператор End \<ключевое\_слово\>](../../../visual-basic/language-reference/statements/end-keyword-statement.md)