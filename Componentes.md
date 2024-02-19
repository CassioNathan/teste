---------------------------------------------------------------------------------------------------------------------------------------------------------------------

#### ```./src/components/:``` Lista de todos os componentes na aplicação

---------------------------------------------------------------------------------------------------------------------------------------------------------------------

#### Amount | ./src/components/Amount:

Componente responsável por exibir o campo de quantidade, juntamente com botões para aumentar ou diminuir essa quantidade.

Tipagem:
```TypeScript
interface IAmountProps {
  onAmountChange: (value: number) => void; // função usada para lidar com a quantidade
  onSubmitEditing: () => void; // função usada ao pressionar enter com o teclado
  initialAmount?: number; // valor inicial do componente
  parametroTelaEvento: string; // Nome da tela para enviar ao google analytics
}
```

Exemplo:
```JSX
<Amount
  ref={amountRef}
  onAmountChange={(quantidade) => {
    setVariavelQueArmazenaQuantidade(quantidade);
  }}
  onSubmitEditing={() => {
    funcaoAoPressionarEnterNoTeclado()
  }}
  parametroTelaEvento="Nome da tela para enviar ao google analytics"
/>
```

![image](https://github.com/lc-sistemas/LC_Coletor_de_dados_APP_V2/assets/147434228/f25c01c4-ba4b-454d-af82-0b26fec7e641)

---------------------------------------------------------------------------------------------------------------------------------------------------------------------

#### Animate Height | .src/components/AnimateHeight:

Componente responsavel por lidar com menus colapsaveis.

Tipagem:
```TypeScript
type Props = {
  children?: React.ReactNode; // componente React filho
  hide?: boolean; // State usado para definir se vai ou não colapsar
  onHeightDidAnimate?: (height: number) => void; // recebe a altura final para executar uma ultima ação EX: Atuaiizar states
  enterFrom?: 'bottom' | 'top'; // direção da animação de abertura
  initialHeight?: number; // altura inicial do componente
} & React.ComponentProps<typeof MotiView>;
```

Exemplo:
```JSX
<AnimateHeight hide={setIsColapsar}>
  (Espaço para declarar componentes)
</AnimateHeight>
```
![image](https://github.com/lc-sistemas/LC_Coletor_de_dados_APP_V2/assets/147434228/e4215630-4f2d-4861-9a0e-3779b16fb517) ![image](https://github.com/lc-sistemas/LC_Coletor_de_dados_APP_V2/assets/147434228/ef129a01-d02e-4396-8758-9038cbdc9c1b)

---------------------------------------------------------------------------------------------------------------------------------------------------------------------

#### Button | ./src/components/buttons:

Componente responsavel por renderizar o botão padrão da aplicação.

Tipagem: 
```TypeScript
interface IButtonProps extends TouchableOpacityProps {
  title: string; // titulo do botão
  backgroundColor?: string; // cor de fundo
  color?: string; // cor principal
  icon?:
    | "save"
    | "add"
    | "search"
    | "check"
    | "import"
    | "export"
    | "filter"
    | "order"
    | "cancel"
    | "grouping"
    | "trash"; // icones disponiveis
  isBlack?: boolean; 
  isLoading?: boolean;
}
```

Exemplo:
```JSX
<Button 
  title="Adicionar"
  icon="add"
  onPress={() => {
    funcaoAExecutar()
  }} 
/>
```

![image](https://github.com/lc-sistemas/LC_Coletor_de_dados_APP_V2/assets/147434228/23502bf1-251e-4f57-ad7c-6553ec9272da)

---------------------------------------------------------------------------------------------------------------------------------------------------------------------

#### Dialog | ./src/components/dialogs:

Componente responsavel por renderizar um caixa de dialogo com o usuario

Tipagem: 
```TypeScript
interface IDialogProps {
  titulo?: string;
  texto?: string;
  visible?: boolean;
  botao1?: string;
  botao2?: string;
  botao3?: string;
  onBackdropPress?: () => void;
  onPress1: () => void;
  onPress2: () => void;
  onPress3: () => void;
  parametroTelaEvento?: string;
}
```

Exemplo:
```JSX
<Dialog
  titulo="Atenção!"
  texto={`Texto de descrição`}
  visible={true}
  botao1="Não"
  botao2="Sim"
  onBackdropPress={() => setIsExibirDialog(false)}
  onPress1={() => setIsExibirDialog(false))
  onPress2={() => {
    setIsExibirDialog(false)
    executarFuncao();
  }}
  onPress3={() => {}}
  parametroTelaEvento= "Nome da tela para enviar ao google analytics"
/>
```

![image](https://github.com/lc-sistemas/LC_Coletor_de_dados_APP_V2/assets/147434228/a64e398c-f235-4605-8af5-3d6e99434f35)

---------------------------------------------------------------------------------------------------------------------------------------------------------------------

#### Fab | ./src/components/FAB: (

Familia de componentes que renderizam um menu flutuante:

*Exemplo no final*

#### Fab Container | ./src/components/FAB/FabContainer:

Componente responsavel por englobar os FabItens.

Tipagem: 
```TypeScript
interface IFabContainerProps {
  children: ReactNode;
  bottom?: number;
  parametroTelaEvento: string;
}
```

Exemplo:
```JSX
<FabContainer parametroTelaEvento="Nome da tela para enviar ao google analytics">
  (Espaço para declarar os FabItens)
</FabContainer>
```

#### Fab Item | ./src/components/FAB/FabItem:

Componente que representa os itens no FabContainer.

Tipagem: 
```TypeScript
interface IFabItemProps {
  title: string;
  type:
    | "add"
    | "search"
    | "save"
    | "delete"
    | "remove"
    | "dollar"
    | "cart"
    | "user"
    | "check"
    | "mark-off"
    | "mark-on"
    | "scan"
    | "order"
    | "filter";
  onPress: () => void;
}
```

Exemplo:
```JSX
  <FabItem
    title={`Nova\nconferência`}
    type="add"
    onPress={() => {
      setIsShowDialogLimparConferencias(true);
    }}
  />
```

(Componente montado FabContainer + FabItem)

![image](https://github.com/lc-sistemas/LC_Coletor_de_dados_APP_V2/assets/147434228/2fff7841-3c2c-488b-b8c8-03ce71705713)

)

---------------------------------------------------------------------------------------------------------------------------------------------------------------------

#### Footer | ./src/components/Footer:

Componente responsavel por exibir as informações de rodapé, como youtube, instagram, facebook.

Tipagem: 
```TypeScript
interface IFooterProps {
  showVersion?: boolean;
  showSocialNetwork?: boolean;
  color?: string;
}
```

Exemplo:
```JSX
<Footer />
```
![image](https://github.com/lc-sistemas/LC_Coletor_de_dados_APP_V2/assets/147434228/234aead2-69be-43d3-9b35-d0028dd825d0)

---------------------------------------------------------------------------------------------------------------------------------------------------------------------

#### Icons | ./src/components/icons:

Icones declarados na aplicação.

Parâmetros: 
{size: Number, color: String}

Declaração:
```JSX
import FontAwesome5 from "@expo/vector-icons/FontAwesome5"; //import da biblioteca, caso necessario

export const Add = ({ size = 22, color = "#fff" }) => {
  return (
    <View>
      <FontAwesome5 name="plus" size={size} color={color} />
    </View>
  );
};
```

Exemplo:
```JSX
<Add size={15} color={color} />
```

---------------------------------------------------------------------------------------------------------------------------------------------------------------------

#### Loading | ./src/components/loading:

Componente responsavel por renderizar um overlay de loading:

Tipagem: 
```TypeScript
interface ILoadingScreenProps {
  backgroundColor?: string;
  descricao?: string;
}
```

Exemplo:
```JSX
{isShowLoading && <LoadingScreen descricao="Importando produtos" />}
```

![image](https://github.com/lc-sistemas/LC_Coletor_de_dados_APP_V2/assets/147434228/f4d260d6-2cac-412f-965a-8c8aec48c53c)

---------------------------------------------------------------------------------------------------------------------------------------------------------------------

#### Modal Cadastro de Produto | ./src/components/modal/ModalCadastroProduto.tsx:

Componente de modal voltado a cadastro de produtos.

Tipagem:
```TypeScript
interface IModalCadastroProdutoProps {
  modalizeRef: any;
  clearSearch: () => void;
}
```

Exemplo:
```JSX
<ModalCadastroProduto
    modalizeRef={modalCadastroProdutoRef}
    clearSearch={() => {funcaoParaLimparCampo()}}
/>
```

![image](https://github.com/lc-sistemas/LC_Coletor_de_dados_APP_V2/assets/147434228/9ca7dd96-a950-4513-9ef0-9099a74c1712)

---------------------------------------------------------------------------------------------------------------------------------------------------------------------

#### Currency Input LC | ./src/components/TextInput/CurrencyInputLc.tsx:

Componente responsavel por renderizar um input para inserir quantidade ou valor(R$).

Tipagem: 
```TypeScript
interface ICurrencyInputLcProps extends CurrencyInputProps {
  ref?: any;
  type?: "quantidade" | "valor";
  textAlign?: "left" | "right" | "center";
  placeHolder?: string;
  value: number;
  precision?: number;
  onChangeText?: (text: any) => void;
  onSubmitEditing?: (
    e: NativeSyntheticEvent<TextInputSubmitEditingEventData>
  ) => void;
  selectTextOnFocus?: boolean;
  editable: boolean;
  backgroundColor?: ColorValue;
}
```

Exemplo:
```JSX
<CurrencyInputLc
    type="quantidade"
    textAlign="center"
    precision={quantidadeFracionada === "SIM" ? 3 : 0}
    editable={true}
    value={quantidade}
    onChangeText={(t) => {
        setQuantidade(Number(t)); //preciso forçar o tipo Number pois ao incrementar ele está concatenando ao invés de somar
    }}
    onSubmitEditing={onSubmitEditing}
/>
```

![image](https://github.com/lc-sistemas/LC_Coletor_de_dados_APP_V2/assets/147434228/e8da34c2-0275-47cf-aa6e-1b34f3d9095f)

---------------------------------------------------------------------------------------------------------------------------------------------------------------------

#### Text Input LC | ./src/components/TextInput/TextInputLc.tsx:

Componente responsavel por renderizar input de texto.

Tipagem:
```TypeScript
interface ITextInputLcProps extends TextInputProps {
  editable?: boolean;
  secureTextEntry?: boolean;
  value: string;
  onChangeText?: (text: string) => void;
  onSubmitEditing?: (
    e: NativeSyntheticEvent<TextInputSubmitEditingEventData>,
  ) => void;
  title: string;
  selectTextOnFocus?: boolean;
  backgroundColor?: ColorValue;
  keyboardType?:
  | 'default'
  | 'numeric'
  | 'email-address'
  | 'ascii-capable'
  | 'numbers-and-punctuation'
  | 'url'
  | 'number-pad'
  | 'phone-pad'
  | 'name-phone-pad'
  | 'decimal-pad'
  | 'twitter'
  | 'web-search'
  | 'visible-password';
  autoFocus?: boolean;
  showBorderBottom?: boolean;
}
```

Exemplo:
```TypeScript
<TextInputLc
    ref={inputRet}
    value={valorNoCampo}
    onChangeText={setValorNoCampo}
    title="Nome"
    backgroundColor="#fff" //Cor de fundo
    onSubmitEditing={() => {
        funcaoAExecutarAoPressionarEnterNoTeclado()
    }}
    returnKeyType="next"
/>
```

![image](https://github.com/lc-sistemas/LC_Coletor_de_dados_APP_V2/assets/147434228/ca356800-4950-4f2d-9c2a-1b1aa3f855ab)

---------------------------------------------------------------------------------------------------------------------------------------------------------------------

#### Text Input Pesquisa | ./src/components/TextInput/TextInputPesquisa.tsx:

Componente responsavel por renderizar um campo de pesquisa com botão lateral.

Tipagem:
```TypeScript
interface ITextInputPesquisaProps extends TextInputProps {
  value: string;
  placeHolder?: string;
  selectTextOnFocus?: boolean;
  showScan?: boolean;
  showCancelOption?: boolean
  keyboardType?: 'default' | 'numeric' | 'email-address';
  onChangeText: (value: string) => void;
  onSubmitEditing: () => void;
  handleShowScan?: () => void;
  han
```

Exemplo:
```JSX
<TextInputPesquisa
    ref={TextInputPesquisaRef}
    showCancelOption={Produto.id > 0} //valida se existe algum produto selecionado
    showScan={true}
    handleShowScan={() => {
        funcaoAExecutarParaAbrirCamera(
    }}
    handleCancel={() => {
        funcaoAExecutarAoPressionarPAraLimparOCampo()
    }}
    value={valorDoCampo}
    onChangeText={setValorDoCampo}
    placeHolder="Interno/Barras"
    selectTextOnFocus
    onSubmitEditing={async () => {
        funcaoAExecutarAoPressionarEnterNoTeclado()
    }}
    keyboardType="numeric"
/>
```

![image](https://github.com/lc-sistemas/LC_Coletor_de_dados_APP_V2/assets/147434228/58886975-b1e0-4642-947a-0b1a86c84c61)

---------------------------------------------------------------------------------------------------------------------------------------------------------------------

#### ToolBar | ./src/components/toolbar/Toolbar.tsx:

Componente responsavel por renderizar a toolbar.

Tipagem: 
```TypeScript
interface IToolbarProps {
  children?: React.ReactElement
  showIconRight?: boolean;
  iconRightName?: string;
  titulo: string;
  iconName?: string;
  iconColor?: string;
  onPress?: (value: any) => void;
  onPressIconRight?: () => void;
  backgroundColor?: string;
}
```
Exemplo:
```JSX
<Toolbar
    titulo="Configurações"
    onPress={() => {
        goBack();
    }}
    iconName="arrow-back"
    showIconRight={true}
>
*Opcional*(Espaço para adicionar componente filho)
</ToolBar>
```

![image](https://github.com/lc-sistemas/LC_Coletor_de_dados_APP_V2/assets/147434228/74b4f836-66ce-4f92-bf49-7300810d088b)

---------------------------------------------------------------------------------------------------------------------------------------------------------------------

#### TourItem | ./src/components/Tour/TourItem.tsx:

Componente responsavel por renderizar um componente de tour, criando um overlay escurecido e rendeizando o componente que deseja destacar por cima com uma descrição.

Tipagem: 
```TypeScript
interface ITourItem {
  children: ReactNode; // componente filho
  posicaoNoTour: number; // valor que define a posição e quando será exibido
  segundaPosicaoNoTour?: number; // valor usado para exibir o componente para complementar outro passo OBS: não irá possuir descrição ou botão
  posicaoDaDescricao?: "esquerda" | "direita" | "cima"; // padrão: baixo
  orientacaoDaDescricao?: "esquerda" | "direita" | "centro"; // padrão: auto
  orientacaoDosBotoesDeAcao?: "coluna" | "linha"; // padrão: linha
  ocultarDescricao?: boolean; // padrão: false
  ocultarFundo?: boolean; // padrão: false
  ocultarBotao?: boolean; // padrão: false
  recalcularDimensoesAntesDeExibir?: boolean; // define se deve recalcular a posição do componente EX: Movimentei a tela ou abri um modal
  executarAntesDeExibir?: () => void; // função a executar antes de exibir o passo EX: Abrir um modal
  executarAntesDeVoltar?: () => void; // função a executar antes de retroceder um passo EX: Fechar um modal
}
```

Exemplo:
```JSX
<TourItem posicaoNoTour={7}>
    (Espaço para declarar o componente que irá fazer parte do tour)               
</TourItem>
```

![image](https://github.com/lc-sistemas/LC_Coletor_de_dados_APP_V2/assets/147434228/68c2d2d6-01c1-497a-879c-3fe4cea37e46)

---------------------------------------------------------------------------------------------------------------------------------------------------------------------
