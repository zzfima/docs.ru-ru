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
ms.openlocfilehash: 9307cf10e6125441bd49baa0e663a5a13f234005
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69944467"
---
# <a name="end-statement"></a>Оператор End
Немедленно завершает выполнение.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
End  
```  
  
## <a name="remarks"></a>Примечания  
 `End` Оператор можно разместить в любом месте процедуры, чтобы принудительно отменить выполнение всего приложения. `End`закрывает все файлы, открытые `Open` с помощью инструкции, и очищает все переменные приложения. Приложение закрывается, как только другие программы не содержат ссылки на свои объекты, и ни один из его кода не выполняется.  
  
> [!NOTE]
> Инструкция останавливает выполнение кода внезапно и не `Dispose` вызывает метод или `Finalize` или любой другой Visual Basic код. `End` Ссылки на объекты, удерживаемые другими программами, становятся недействительными. Если оператор обнаруживается `Try` внутри блока или `Catch` , управление передается в соответствующий `Finally` блок. `End`  
  
 Инструкция приостанавливает выполнение, но в отличие от `End`этого она не закрывает никакие файлы и не очищает переменные, если она не обнаружена в скомпилированном исполняемом файле (exe). `Stop`  
  
 Поскольку `End` завершает работу приложения, не прибегая к открытым ресурсам, перед его использованием следует попытаться закрыться аккуратно. Например, если приложение имеет открытые формы, необходимо закрыть их, прежде чем управление достигнет `End` оператора.  
  
 Следует использовать `End` с осторожностью и только тогда, когда необходимо немедленно приостанавливаться. Обычные способы завершения процедуры ([инструкция return](../../../visual-basic/language-reference/statements/return-statement.md) и [оператор Exit](../../../visual-basic/language-reference/statements/exit-statement.md)) не только аккуратно закрывают процедуру, но и выдают вызывающему коду возможность аккуратно закрыться. Например, консольное приложение может просто `Return` `Main` выполнить процедуру.  
  
> [!IMPORTANT]
> `End` Оператор<xref:System.Environment.Exit%2A> вызывает метод<xref:System.Environment> класса в<xref:System> пространстве имен. <xref:System.Environment.Exit%2A>требует наличия `UnmanagedCode` разрешений. В <xref:System.Security.SecurityException> противном случае возникает ошибка.  
  
 Если за ним следует дополнительное ключевое слово, [оператор End \<ключевое_слово >](../../../visual-basic/language-reference/statements/end-keyword-statement.md) выделяют конец определения соответствующей процедуры или блока. Например, `End Function` завершает определение `Function` процедуры.  
  
## <a name="example"></a>Пример  
 В следующем примере `End` оператор используется для завершения выполнения кода, если пользователь запрашивает его.  
  
 [!code-vb[VbVersHelp60Controls#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVersHelp60Controls/VB/Form1.vb#64)]  
  
## <a name="smart-device-developer-notes"></a>Примечания для разработчиков смарт-устройств  
 Эта инструкция не поддерживается.  
  
## <a name="see-also"></a>См. также

- <xref:System.Security.Permissions.SecurityPermissionFlag>
- [Оператор Stop](../../../visual-basic/language-reference/statements/stop-statement.md)
- [End \<ключевое слово > оператор](../../../visual-basic/language-reference/statements/end-keyword-statement.md)
