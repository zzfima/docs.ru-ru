---
title: Объект My.Forms (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- My.Forms
- My.MyProject.Forms
helpviewer_keywords:
- My.Forms object
ms.assetid: f6bff4e6-6769-4294-956b-037aa6106d2a
ms.openlocfilehash: d15765b7673f321d4362ceea0adb73959a7e7726
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2018
ms.locfileid: "45591975"
---
# <a name="myforms-object"></a>Объект My.Forms
Предоставляет свойства для доступа к экземпляру каждой формы Windows, объявленные в текущем проекте.  
  
## <a name="remarks"></a>Примечания  
 `My.Forms` Объект предоставляет экземпляр каждой формы в текущем проекте. Имя свойства совпадает с именем формы, к которой обращается свойство.   
  
 Можно воспользоваться формами, предоставляемые `My.Forms` объекта, используя имя в формате без уточнения. Так как имя свойства совпадает с именем типа формы, это дает возможность доступа к форме, как если бы она имела экземпляр по умолчанию. Например, предложение `My.Forms.Form1.Show` эквивалентно предложению `Form1.Show`.  
  
 `My.Forms` Объект предоставляет только формы, связанные с текущим проектом. Она предоставляет доступ к формам, объявленным в указанные библиотеки DLL. Чтобы получить доступ к форме, библиотеки DLL, необходимо использовать полное имя формы, которое *DllName*. *FormName*.  
  
 Можно использовать <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A> свойство, чтобы получить коллекцию всех открытых форм приложения.  
  
 Объект и его свойства доступны только для приложений Windows.  
  
## <a name="properties"></a>Свойства  
 Каждое свойство `My.Forms` объект предоставляет доступ к экземпляру формы в текущем проекте. Имя свойства совпадает имя формы, который обращается к свойству, а тип свойства совпадает с типом формы.  
  
> [!NOTE]
>  Если имеется конфликт имен, имя свойства для доступа к форме является *RootNamespace*_*пространства имен*\_*FormName*. Например, рассмотрим две формы с именем `Form1.`Если одна из этих форм находится в корневом пространстве имен `WindowsApplication1` и в пространстве имен `Namespace1`, доступ к этой форме через `My.Forms.WindowsApplication1_Namespace1_Form1`.  
  
 `My.Forms` Объект предоставляет доступ к экземпляру главной формы приложения, который был создан во время запуска. Для всех остальных форм `My.Forms` объекта создает новый экземпляр формы, когда она доступна и сохраняет его. Последующие попытки доступа к этому свойству возвращают этот экземпляр формы.  
  
 Можно уничтожить форму путем назначения `Nothing` свойства для этой формы. Вызовы метода задания свойства <xref:System.Windows.Forms.Form.Close%2A> метод формы, а затем назначает `Nothing` к сохраненному значению. Если назначить любое значение, отличное от `Nothing` свойству, метод задания значения создает исключение <xref:System.ArgumentException> исключение.  
  
 Вы можете протестировать свойство `My.Forms` объект сохраняет экземпляр формы с помощью `Is` или `IsNot` оператор. Эти операторы можно использовать для проверки, является ли значение свойства `Nothing`.  
  
> [!NOTE]
>  Как правило `Is` или `IsNot` оператор имеет считывается значение свойства для выполнения сравнения. Тем не менее если это свойство в настоящее время сохраняет `Nothing`, свойство создает новый экземпляр формы и затем возвращает этот экземпляр. Тем не менее, компилятор Visual Basic обрабатывает свойства `My.Forms` объект по-разному и позволяет `Is` или `IsNot` оператор, чтобы проверить состояние свойства без изменения его значения.  
  
## <a name="example"></a>Пример  
 В этом примере заголовок окна меняется на значение по умолчанию `SidebarMenu` формы.  
  
 [!code-vb[VbVbalrMyForms#2](../../../visual-basic/language-reference/objects/codesnippet/VisualBasic/my-forms-object_1.vb)]  
  
 Для работы этого примера проекта должен иметь форму с именем `SidebarMenu`.  
  
 Этот код будет работать только в проекте приложения Windows.  
  
## <a name="requirements"></a>Требования  
  
### <a name="availability-by-project-type"></a>Доступность по типу проекта  
  
|Тип проекта|Доступно|  
|---|---|  
|Приложение Windows|**Да**|  
|Библиотека классов|Нет|  
|Консольное приложение|Нет|  
|Библиотека элементов управления Windows|Нет|  
|Web Control Library|Нет|  
|Служба Windows|Нет|  
|Веб-сайт|Нет|  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A>  
 <xref:System.Windows.Forms.Form>  
 <xref:System.Windows.Forms.Form.Close%2A>  
 [Объекты](../../../visual-basic/language-reference/objects/index.md)  
 [Оператор Is](../../../visual-basic/language-reference/operators/is-operator.md)  
 [Оператор IsNot](../../../visual-basic/language-reference/operators/isnot-operator.md)  
 [Доступ к формам приложения](../../../visual-basic/developing-apps/programming/accessing-application-forms.md)
