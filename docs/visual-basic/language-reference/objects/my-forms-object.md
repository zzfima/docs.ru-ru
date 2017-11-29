---
title: "Объект My.Forms"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- My.Forms
- My.MyProject.Forms
helpviewer_keywords: My.Forms object
ms.assetid: f6bff4e6-6769-4294-956b-037aa6106d2a
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a5aa7af1f07a29660335d968c1ecc17be5f8beec
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="myforms-object"></a>Объект My.Forms
Предоставляет свойства для доступа к экземпляру каждой формы Windows Forms, объявленные в текущем проекте.  
  
## <a name="remarks"></a>Примечания  
 `My.Forms` Объект предоставляет экземпляр каждой формы в текущем проекте. Имя свойства совпадает с именем формы, которая обращается к свойству. Сведения о добавлении формы в проект см. в разделе [как: добавить Windows Forms в проект](http://msdn.microsoft.com/en-us/3d7bb25f-fd90-47cf-9378-fa0d764686c1).  
  
 Можно воспользоваться формами, предоставляемые `My.Forms` с использованием имени формы без уточнения. Поскольку имя свойства совпадает с именем типа формы, это дает возможность доступа к форме, как если бы она имела экземпляр по умолчанию. Например, предложение `My.Forms.Form1.Show` эквивалентно предложению `Form1.Show`.  
  
 `My.Forms` Объект предоставляет только формы, связанные с текущим проектом. Он не предоставляет доступ к формам, объявленным в DLL, на которую указывает ссылка. Чтобы получить доступ к форме, библиотеки DLL, необходимо использовать полное имя формы, которое *DllName*. *Имя_формы*.  
  
 Можно использовать <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A> свойство для получения коллекции всех открытых форм приложения.  
  
 Объект и его свойства доступны только для приложений Windows.  
  
## <a name="properties"></a>Свойства  
 Каждое свойство `My.Forms` объект предоставляет доступ к экземпляру формы в текущем проекте. Имя свойства совпадает имя формы, который обращается к свойству, а тип свойства совпадает с типом формы.  
  
> [!NOTE]
>  Если имеется конфликт имен, имя свойства для доступа к форме является *RootNamespace*_*имен*\_*Имя_формы*. Например, рассмотрим две формы с именем `Form1.`Если одна из этих форм находится в корневом пространстве имен `WindowsApplication1` и в пространстве имен `Namespace1`, доступ к форме с использованием `My.Forms.WindowsApplication1_Namespace1_Form1`.  
  
 `My.Forms` Объект предоставляет доступ к экземпляру приложения главной формы, созданной при запуске. Для всех других форм `My.Forms` объект создает новый экземпляр формы, если она доступна и сохраняет его. Последующие попытки доступа к этому свойству возвращают этот экземпляр формы.  
  
 Формы можно освободить путем назначения `Nothing` свойства для этой формы. Вызовы метода задания свойства <xref:System.Windows.Forms.Form.Close%2A> метод формы, а затем назначает `Nothing` с сохраненным значением. Если присвоить любое значение, отличное от `Nothing` к свойству, методу задания создает исключение <xref:System.ArgumentException> исключение.  
  
 Можно проверить, является ли свойство `My.Forms` объект сохраняет экземпляр формы с помощью `Is` или `IsNot` оператор. Эти операторы можно использовать для проверки, если значение свойства `Nothing`.  
  
> [!NOTE]
>  Как правило `Is` или `IsNot` оператор имеет считывается значение свойства для выполнения сравнения. Тем не менее если в настоящее время хранит свойство `Nothing`, свойство создает новый экземпляр формы и затем возвращает этот экземпляр. Однако компилятор Visual Basic обрабатывает свойства `My.Forms` объект по-разному и позволяет `Is` или `IsNot` проверить состояние свойства без изменения его значения.  
  
## <a name="example"></a>Пример  
 В этом примере изменяется заголовок по умолчанию `SidebarMenu` формы.  
  
 [!code-vb[VbVbalrMyForms#2](../../../visual-basic/language-reference/objects/codesnippet/VisualBasic/my-forms-object_1.vb)]  
  
 Для работы этого примера проект должен иметь форму с именем `SidebarMenu`. Дополнительные сведения см. в разделе [как: добавить Windows Forms в проект](http://msdn.microsoft.com/en-us/3d7bb25f-fd90-47cf-9378-fa0d764686c1).  
  
 Этот код будет работать только в проекте приложения Windows.  
  
## <a name="requirements"></a>Требования  
  
### <a name="availability-by-project-type"></a>Доступность по типу проекта  
  
|Тип проекта|Доступно|  
|---|---|  
|Приложение Windows|**Да**|  
|Библиотека классов|Нет|  
|Консольное приложение|Нет|  
|Библиотека элементов управления Windows|Нет|  
|Библиотека веб-элементов управления|Нет|  
|Служба Windows|Нет|  
|Веб-сайт|Нет|  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A>  
 <xref:System.Windows.Forms.Form>  
 <xref:System.Windows.Forms.Form.Close%2A>  
 [Объекты](../../../visual-basic/language-reference/objects/index.md)  
 [Способ: добавить в проект Windows Forms](http://msdn.microsoft.com/en-us/3d7bb25f-fd90-47cf-9378-fa0d764686c1)  
 [Оператор Is](../../../visual-basic/language-reference/operators/is-operator.md)  
 [Оператор IsNot](../../../visual-basic/language-reference/operators/isnot-operator.md)  
 [Доступ к формам приложения](../../../visual-basic/developing-apps/programming/accessing-application-forms.md)
