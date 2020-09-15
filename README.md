# Inlämning 1 - Computer

### Förberedelsefrågor

1. **Klasser:** `Memory`, `Program`, `ByteWord`, `LongWord`, `ByteWordFactory`, `LongWordFactory`, `Address`, `Add`, `Mul`, `Halt`, `Print`, `Jump`, `JumpEq`, `Copy`, `BinOp`

   **Gränssnitt:** `Instruction`, `Word`, `WordFactory`

2. Man skulle kunna utvidga `List`. Ger dock inte stort syfte då `add` metoden för `Program` inte är så komplex.

3. `internal`**:** `Memory`, `Computer`, `Program` 

   `input`**:** `Word`, `ByteWord`, `LongWord`, `Address`, `WordFactory`, `ByteWordFactory`, `LongWordFactory`

   `instruction`**:** `Add`, `Mul`, `Halt`, `Print`, `Jump`, `JumpEq`, `Copy`, `Instruction`, `BinOp`

4. Det bör användas för att applicera de sju instruktioner. Mönstret gör det enkelt för folk att utvidga programmet med nya instruktioner. Man behöver då endast skriva en klass som implementerar `Instruction`. Det låter dessutom alla instruktioner anropas via samma metod, `execute`.

5. Det blir aktuellt för instruktionerna `Add` och `Mul` där dessa kan förenklas genom att introducera en abstrakt klass `BinOp` som de utvigdar. Klassen möjliggör för enkla tillägg av binära operationer såsom division, subtraktion etc. då man endast behöver utvidga `BinOp` och skriva den enkla operationen.

6. Genom att skapa ett interface `Word` och låter den vara "hårdkodad" så möjliggör det för nya typer av ord förutom `ByteWord` och `LongWord`. Nya ord kan enkelt läggas in genom att implementera interfacet.

7. I klassen `Add`.

8. Ett av de två factories bör kuva det andra. I detta fallet bör *lwf* kuva *bwf* eftersom en `Long`kan uttrycka alla möjliga `Byte` tal pga dess större intervall. 
