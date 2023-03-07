# Realidade Aumentada Unity

### Aplicação Simples de Realidade Aumentada com Unity + Vuforia
 
Este projeto utiliza o Unity e o Vuforia, que viabilizam o uso de realidade aumentada.

### Para começar, será necessário baixar o Vuforia Engine
[Baixar o Vuforia](https://developer.vuforia.com/user/login?url=/downloads/sdk%3F_%3D1678117884)

Será preciso criar uma conta e uma licença para registrar o alvo (target).

Após subir o alvo desejado, será possível visualizar o mapeamento como na imagem abaixo:

<img width="500" src="https://i.ibb.co/zFQyWR8/print1.jpg">

Feito isso, basta baixar o banco de dados.

Em seguida, monte sua centa com o Imagem Target e a Câmera AR:

<img width="500" src="https://i.ibb.co/02L13Dk/Anima-o.gif">

#### Adicione o script ao cubo para fazê-lo rotacionar

```csharp
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class ScriptRotacionar : MonoBehaviour
{
    public Vector3 rotateAmount;
    void Start()
    {
        
    }

    void Update()
    {
        transform.Rotate(rotateAmount * Time.deltaTime);
    }
}
```
Em seguida, altere os valores:

<img width="500" src="https://i.ibb.co/hmjd1Q8/Captura-de-tela-2023-03-06-210413.png">

Para adicionar os controles via teclado, crie um script com o nome Movimento e adicione ao cubo.


```csharp
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class Movimento : MonoBehaviour
{
    Vector3 Vec;
    void Start()
    {
    }

    void Update()
    {
        Vec = transform.localPosition;
        Vec.y += Input.GetAxis("Jump") * Time.deltaTime * 5;
        Vec.x += Input.GetAxis("Horizontal") * Time.deltaTime * 5;
        Vec.z += Input.GetAxis("Vertical") * Time.deltaTime * 5;
        transform.localPosition = Vec;
    }
}

```


#### Para adicionar a gravidade

Adicione um elemento Cube com o nome *Plano* conforme a imagem:

<img src="https://i.ibb.co/RSnDL9R/plano.jpg">


A hierarquia deve ser disposta como na imagem a seguir:

<img src="https://i.ibb.co/7N98wsw/hierarquia.jpg">



No elemento Cube adicione um componente "Rigidbody" no botão "Add Component" no Inspector:


<img src="https://i.ibb.co/k2S0mDy/add-component.png">

Para habilitar a gravidade, basta marcar a opção "Use Gravity":

<img src="https://i.ibb.co/cb4F1sQ/elemento-fisico.jpg">
