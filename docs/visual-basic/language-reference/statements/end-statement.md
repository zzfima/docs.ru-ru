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
ms.openlocfilehash: cb2fb4abb21b7b9c6575cec4aca1374f63687607
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343726"
---
# <a name="end-statement"></a>Оператор End
Немедленно завершает выполнение.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
End  
```  
  
## <a name="remarks"></a>Заметки  
 Можно поместить оператор `End` в любую процедуру, чтобы принудительно отменить выполнение всего приложения. `End` закрывает все файлы, открытые с помощью инструкции `Open`, и очищает все переменные приложения. Приложение закрывается, как только другие программы не содержат ссылки на свои объекты, и ни один из его кода не выполняется.  
  
> [!NOTE]
> Оператор `End` неожиданно останавливает выполнение кода и не вызывает метод `Dispose` или `Finalize` или любой другой код Visual Basic. Ссылки на объекты, удерживаемые другими программами, становятся недействительными. Если в блоке `Try` или `Catch` обнаруживается оператор `End`, управление не передается соответствующему блоку `Finally`.  
  
 Инструкция `Stop` приостанавливает выполнение, но в отличие от `End`, она не закрывает никакие файлы и не очищает переменные, если только она не обнаружена в скомпилированном исполняемом файле (exe).  
  
 Поскольку `End` прекращает работу приложения, не прибегая к каким-либо ресурсам, которые могут быть открыты, следует сначала попытаться закрыть его перед использованием. Например, если приложение имеет открытые формы, необходимо закрыть их, прежде чем управление достигнет оператора `End`.  
  
 Следует использовать `End` с осторожностью и только тогда, когда необходимо немедленно останавливаться. Обычные способы завершения процедуры ([инструкция return](../../../visual-basic/language-reference/statements/return-statement.md) и [оператор Exit](../../../visual-basic/language-reference/statements/exit-statement.md)) не только аккуратно закрывают процедуру, но и выдают вызывающему коду возможность аккуратно закрыться. Например, консольное приложение может просто `Return` из процедуры `Main`.  
  
> [!IMPORTANT]
> Оператор `End` вызывает метод <xref:System.Environment.Exit%2A> класса <xref:System.Environment> в пространстве имен <xref:System>. <xref:System.Environment.Exit%2A> требуется разрешение `UnmanagedCode`. В противном случае возникает ошибка <xref:System.Security.SecurityException>.  
  
 Если за ним следует дополнительное ключевое слово, [оператор end \<ключевое слово >](../../../visual-basic/language-reference/statements/end-keyword-statement.md) выделяют конец определения соответствующей процедуры или блока. Например, `End Function` завершает определение `Function` процедуры.  
  
## <a name="example"></a>Пример  
 В следующем примере оператор `End` используется для завершения выполнения кода, если пользователь запрашивает его.  
  
 [!code-vb[VbVersHelp60Controls#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVersHelp60Controls/VB/Form1.vb#64)]  
  
## <a name="smart-device-developer-notes"></a>Примечания для разработчиков смарт-устройств  
 Эта инструкция не поддерживается.  
  
## <a name="see-also"></a>См. также

- <xref:System.Security.Permissions.SecurityPermissionFlag>
- [Оператор Stop](../../../visual-basic/language-reference/statements/stop-statement.md)
- [End \<ключевое слово >](../../../visual-basic/language-reference/statements/end-keyword-statement.md)
