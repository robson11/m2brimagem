Página de apresentação do manual / capa.

# Introdução #

## class.imagem.php ##

  * **versão:** 6.2
  * **Autores:**  Davi Tavares Ferreira
  * [www.m2brnet.com](http://www.m2brnet.com)

## O que faz atualmente? ##

  * converte imagens
  * redimensiona imagens, mantendo proporção
  * flip horizontal / vertical
  * girar imagem
  * marca d'água texto
  * marca d'água (imagem)
  * marca d'água com posicionamento fixo

## Falta implementar ##

  * cropagem (sem redimensionamento)
  * posicionamento das marcas d'água por porcentagem (?)
  * cor de fundo na legenda em texto (?)
  * resize por porcentagem (extends?)
  * crop por porcentagem (extends?)

## Exemplo de uso: ##
```
// include da classe imagem
include('class.m2brimagem.php');

// instancia objeto e carrega imagem
$oImg = new imagem('3.jpg');
// valida imagem
$valida = $oImg->valida();

if ($valida == 'OK') {
	// redimensiona imagem, cropando
	$oImg->redimensiona(400,200,'crop','');
	// flipa imagem horizontalmente
	$oImg->flip('h');
	// define cor da legenda
	$rgb	= array(255,255,255);
	// adiciona legenda em texto
	$oImg->legenda('scarlett johansson','11','20','20',$rgb,true,'ariblk.ttf');
	// adiciona marca d'água
	$oImg->marca('marca.png',40,100,100);
	// cria imagem de saída no browser, sem salvar
	$oImg->geraDestino('1.png',false);
} else {
	// imagem inválida
	die($valida);
}	
```

## Mais em: ##
http://www.daviferreira.com/blog/2007/09/07/classe-imagem-php.html