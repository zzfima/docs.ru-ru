---
title: Оператор End
ms.date: 07/20/2015
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
ms.openlocfilehash: 864ac5ef1713f8ffa93c18accede8ecd5b3b7a8c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604436"
---
# <a name="end-statement"></a>Оператор End
Немедленно прекращает выполнение.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
End  
```  
  
## <a name="remarks"></a>Примечания  
 Можно поместить `End` инструкции в любом месте процедуры для принудительного завершения работы всего приложения. `End` Закрывает все файлы, открытые с `Open` инструкции и очищает все переменные приложения. Приложение закрывается сразу нет других программ, поддерживающих ссылки на его объекты, и его код не выполняются.  
  
> [!NOTE]
>  `End` Инструкция немедленно прекращает выполнение кода и не вызывает `Dispose` или `Finalize` метода или любого другого кода в Visual Basic. Ссылки на объекты, хранящиеся в других программах, становятся недействительными. Если `End` встречается в `Try` или `Catch` в соответствующий блок управления не проходит `Finally` блока.  
  
 `Stop` Оператор приостанавливает выполнение, но в отличие от `End`, не закрывает файлы и не удаляет переменные, если только встречается в компилируемый исполняемый файл (.exe) файл.  
  
 Поскольку `End` завершает приложение, не обращая внимания к ресурсам, которые могут быть открыты, следует попытаться закрытия без ошибок, перед его использованием. Например, если приложение имеет открытые формы, их следует закрыть перед управления достигает `End` инструкции.  
  
 Следует использовать `End` только в случае необходимости и только при необходимости для немедленной остановки. Обычным способом, чтобы завершить процедуру ([оператор Return](../../../visual-basic/language-reference/statements/return-statement.md) и [оператор Exit](../../../visual-basic/language-reference/statements/exit-statement.md)) не только аккуратно закрыть процедуры, но также предоставить возможность закрытия аккуратно вызывающий код. В консольном приложении, например, можно просто `Return` из `Main` процедуры.  
  
> [!IMPORTANT]
>  `End` Инструкция вызывает <xref:System.Environment.Exit%2A> метод <xref:System.Environment> класса в <xref:System> пространства имен. <xref:System.Environment.Exit%2A> требует наличия `UnmanagedCode` разрешение. Если нет, <xref:System.Security.SecurityException> возникает ошибка.  
  
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
