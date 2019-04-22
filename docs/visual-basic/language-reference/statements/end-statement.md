---
title: Оператор End (Visual Basic)
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
ms.openlocfilehash: 4fc4fd36fb6b057195e9d8a79eb0a5b3ac9ff95c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58832025"
---
# <a name="end-statement"></a>Оператор End
Немедленно прекращает выполнение.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
End  
```  
  
## <a name="remarks"></a>Примечания  
 Вы можете поместить `End` инструкции в любом месте процедуры, чтобы принудительно остановить работу всего приложения. `End` Закрывает все файлы, открытые с `Open` инструкции и очищает все переменные приложения. Приложение закрывается сразу нет других программ, поддерживающих ссылки на его объекты и выполняется код.  
  
> [!NOTE]
>  `End` Инструкция немедленно прерывается выполнение кода и не вызывает `Dispose` или `Finalize` метода или любого другого кода Visual Basic. Ссылки на объекты, хранящиеся в других программах, становятся недействительными. Если `End` встречается в `Try` или `Catch` блок, элемент управления не проходит в соответствующий `Finally` блока.  
  
 `Stop` Инструкция приостанавливает выполнение, но в отличие от `End`, закройте все файлы или не удаляет переменные, в том случае, если только встречается в файле скомпилированный исполняемый файл (.exe).  
  
 Так как `End` завершает работу приложения, не обращая внимания к любым ресурсам, которые могут быть открыты, следует попытаться закрытием аккуратно, перед его использованием. Например, если приложение содержит открытые формы, их следует закрыть перед управления достигает `End` инструкции.  
  
 Следует использовать `End` только в случае необходимости и только при необходимости для немедленной остановки. Обычным способом, чтобы завершить процедуру ([оператор Return](../../../visual-basic/language-reference/statements/return-statement.md) и [оператор Exit](../../../visual-basic/language-reference/statements/exit-statement.md)) не только аккуратно закрыть процедуру, но также дают возможность закрытия аккуратно вызывающий код. В консольном приложении, например, можно просто `Return` из `Main` процедуры.  
  
> [!IMPORTANT]
>  `End` Инструкция вызывает <xref:System.Environment.Exit%2A> метод <xref:System.Environment> в класс <xref:System> пространства имен. <xref:System.Environment.Exit%2A> необходимо иметь `UnmanagedCode` разрешение. Если вы этого не сделать, <xref:System.Security.SecurityException> возникает ошибка.  
  
 Если за ним дополнительных ключевых слов, следует [окончания \<ключевое слово > инструкции](../../../visual-basic/language-reference/statements/end-keyword-statement.md) отделяет конец определения соответствующей процедуры или блока. Например `End Function` завершает определение `Function` процедуры.  
  
## <a name="example"></a>Пример  
 В следующем примере используется `End` инструкции для завершения выполнения кода в том случае, если пользователь запрашивает его.  
  
 [!code-vb[VbVersHelp60Controls#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVersHelp60Controls/VB/Form1.vb#64)]  
  
## <a name="smart-device-developer-notes"></a>Примечания для разработчиков смарт-устройств  
 Эта инструкция не поддерживается.  
  
## <a name="see-also"></a>См. также

- <xref:System.Security.Permissions.SecurityPermissionFlag>
- [Оператор Stop](../../../visual-basic/language-reference/statements/stop-statement.md)
- [Конец \<ключевое слово > инструкции](../../../visual-basic/language-reference/statements/end-keyword-statement.md)
