---
title: Использование действия Switch с пользовательскими типами
ms.date: 03/30/2017
ms.assetid: 482a48c4-eb83-40c3-a4e2-2f9a8af88b75
ms.openlocfilehash: 2b6f3109324064cb5e746de9c61e5a70c4c4d60b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33517885"
---
# <a name="usage-of-the-switch-activity-with-custom-types"></a>Использование действия Switch с пользовательскими типами
В этом образце описывается способ включения действия <xref:System.Activities.Statements.Switch%601> для оценки определяемого пользователем сложного типа во время выполнения. В большинстве традиционных процедурных языков программирования [переключения](http://go.microsoft.com/fwlink/?LinkId=180521) инструкция выбирает логику выполнения на основе условного вычисления переменной. Обычно оператор `switch` работает с выражением, которое может быть оценено статически. Например, в C# это означает, что поддерживаются только примитивные типы, такие как <xref:System.Boolean>, <xref:System.Int32>, <xref:System.String> и типы перечисления.  
  
 Для поддержки переключения для пользовательского класса необходимо реализовать логику, которая оценивает значения пользовательского сложного типа во время выполнения. Этот образец демонстрирует, реализацию переключения по пользовательскому сложному типу, называемому `Person`.  
  
-   В пользовательском классе атрибут `Person`, a <xref:System.ComponentModel.TypeConverter> объявлен с именем пользовательского объекта <xref:System.ComponentModel.TypeConverter>.  
  
    ```  
    [TypeConverter(typeof(PersonConverter))]  
    public class Person  
    {  
       public string Name { get; set; }  
       public int Age { get; set; }  
    ...  
    ```  
  
-   В пользовательском классе `Person` переопределены классы <xref:System.Object.Equals%2A> и <xref:System.Object.GetHashCode%2A>.  
  
    ```  
    public override bool Equals(object obj)  
    {  
        Person person = obj as Person;  
  
        if (person != null)  
        {  
            return string.Equals(this.Name, person.Name);  
        }  
  
        return false;  
    }  
  
    public override int GetHashCode()  
    {  
        if (this.Name != null)  
        {  
            return this.Name.GetHashCode();  
        }  
  
        return 0;  
    }  
    ```  
  
-   Реализован пользовательский класс <xref:System.ComponentModel.TypeConverter>, который выполняет преобразование экземпляра пользовательского класса в строку, а строки - в экземпляр пользовательского класса.  
  
    ```  
    public class PersonConverter : TypeConverter  
    {  
        public override bool CanConvertFrom(ITypeDescriptorContext context,  
           Type sourceType)  
        {  
            return (sourceType is string);  
        }  
  
        // Overrides the ConvertFrom method of TypeConverter.  
        public override object ConvertFrom(ITypeDescriptorContext context,  
           CultureInfo culture, object value)  
        {  
            if (value == null)  
            {  
                return null;  
            }  
  
            if (value is string)  
            {  
                return new Person  
                {  
                    Name = (string)value  
                };  
            }  
  
            return base.ConvertFrom(context, culture, value);  
        }  
  
        // Overrides the ConvertTo method of TypeConverter.  
        public override object ConvertTo(ITypeDescriptorContext context,  
           CultureInfo culture, object value, Type destinationType)  
        {  
            if (destinationType == typeof(string))  
            {  
                if (value != null)  
                {  
                    return ((Person) value).Name;  
                }  
                else  
                {  
                    return null;  
                }  
            }  
  
            return base.ConvertTo(context, culture, value, destinationType);  
        }  
    }  
    ```  
  
 В этот образец включены следующие файлы.  
  
-   **Person.cs**: определяет `Person` класса.  
  
-   **PersonConverter.cs**: преобразователь типов для `Person` класса.  
  
-   **Sequence.XAML**: рабочий процесс, который переключается `Person` типа.  
  
-   **Program.cs**: основная функция, которая запускает рабочий процесс.  
  
#### <a name="to-use-this-sample"></a>Использование этого образца  
  
1.  Загрузите Switch.sln в [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Чтобы построить решение, нажмите CTRL+SHIFT+B.  
  
3.  Чтобы запустить образец, нажмите клавиши CTRL+F5.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцов. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\Switch`  
  
## <a name="see-also"></a>См. также  
 [Встроенная библиотека действий](../../../../docs/framework/windows-workflow-foundation/net-framework-4-5-built-in-activity-library.md)
