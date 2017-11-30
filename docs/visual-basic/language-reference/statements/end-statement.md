---
title: "Оператор End"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.End
- End
helpviewer_keywords:
- execution [Visual Basic], ending
- files [Visual Basic], closing
- End keyword [Visual Basic], End statements
- programs [Visual Basic], quitting
- code, exiting
- program termination
- End statement [Visual Basic]
- execution [Visual Basic], stopping
ms.assetid: 0e64467c-0f34-4aab-9ddd-43f8b9d55d90
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b692409f2895f5e9b713c57fc35ff2def40bce75
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="end-statement"></a>Оператор End
Немедленно прекращает выполнение.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
End  
```  
  
## <a name="remarks"></a>Примечания  
 Можно поместить `End` инструкции в любом месте процедуры для принудительного завершения работы всего приложения. `End`Закрывает все файлы, открытые с `Open` инструкции и очищает все переменные приложения. Приложение закрывается сразу нет других программ, поддерживающих ссылки на его объекты, и его код не выполняются.  
  
> [!NOTE]
>  `End` Инструкция немедленно прекращает выполнение кода и не вызывает `Dispose` или `Finalize` метода или любого другого кода в Visual Basic. Ссылки на объекты, хранящиеся в других программах, становятся недействительными. Если `End` встречается в `Try` или `Catch` в соответствующий блок управления не проходит `Finally` блока.  
  
 `Stop` Оператор приостанавливает выполнение, но в отличие от `End`, не закрывает файлы и не удаляет переменные, если только встречается в компилируемый исполняемый файл (.exe) файл.  
  
 Поскольку `End` завершает приложение, не обращая внимания к ресурсам, которые могут быть открыты, следует попытаться закрытия без ошибок, перед его использованием. Например, если приложение имеет открытые формы, их следует закрыть перед управления достигает `End` инструкции.  
  
 Следует использовать `End` только в случае необходимости и только при необходимости для немедленной остановки. Обычным способом, чтобы завершить процедуру ([оператор Return](../../../visual-basic/language-reference/statements/return-statement.md) и [оператор Exit](../../../visual-basic/language-reference/statements/exit-statement.md)) не только аккуратно закрыть процедуры, но также предоставить возможность закрытия аккуратно вызывающий код. В консольном приложении, например, можно просто `Return` из `Main` процедуры.  
  
> [!IMPORTANT]
>  `End` Инструкция вызывает <xref:System.Environment.Exit%2A> метод <xref:System.Environment> класса в <xref:System> пространства имен. <xref:System.Environment.Exit%2A>требует наличия `UnmanagedCode` разрешение. Если нет, <xref:System.Security.SecurityException> возникает ошибка.  
  
 Если за ним следует дополнительных ключевых слов, [окончания \<ключевое слово > инструкции](../../../visual-basic/language-reference/statements/end-keyword-statement.md) отделяет конец определения соответствующей процедуры или блока. Например `End Function` завершает определение `Function` процедуры.  
  
## <a name="example"></a>Пример  
 В следующем примере используется `End` инструкции для завершения выполнения по требованию пользователя.  
  
 [!code-vb[VbVersHelp60Controls#64](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/end-statement_1.vb)]  
  
## <a name="smart-device-developer-notes"></a>Примечания для разработчиков интеллектуальных устройств  
 Эта инструкция не поддерживается.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Security.Permissions.SecurityPermissionFlag>  
 [Оператор Stop](../../../visual-basic/language-reference/statements/stop-statement.md)  
 [Конец \<ключевое слово > инструкции](../../../visual-basic/language-reference/statements/end-keyword-statement.md)
