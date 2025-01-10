import Image from 'next/image'
import { Card, CardContent } from "@/components/ui/card"
import { ScrollArea } from "@/components/ui/scroll-area"

const characters = [
  {
    name: "Vincent Vega",
    description: "Asesino a sueldo con estilo, adicto a la heroína y fanático de los autos clásicos. Su pasión por el baile es tan intensa como su lealtad a Marsellus Wallace.",
    image: "/placeholder.svg?height=300&width=200"
  },
  {
    name: "Jules Winnfield",
    description: "Compañero de Vincent, conocido por su intensidad y sus monólogos bíblicos. Experimenta una epifanía que cambia su vida durante la película.",
    image: "/placeholder.svg?height=300&width=200"
  },
  {
    name: "Mia Wallace",
    description: "Esposa de Marsellus Wallace, ex-actriz y adicta a la cocaína. Su química con Vincent Vega lleva a una de las escenas de baile más icónicas del cine.",
    image: "/placeholder.svg?height=300&width=200"
  },
  {
    name: "Butch Coolidge",
    description: "Boxeador que se niega a perder una pelea amañada, desatando la ira de Marsellus Wallace. Su lealtad a un reloj familiar lo mete en problemas.",
    image: "/placeholder.svg?height=300&width=200"
  },
  {
    name: "Marsellus Wallace",
    description: "Poderoso jefe del crimen de Los Ángeles. Su presencia intimidante se siente a lo largo de la película, aunque rara vez se le ve directamente.",
    image: "/placeholder.svg?height=300&width=200"
  },
]

export default function PulpFictionCharacters() {
  return (
    <div className="min-h-screen bg-yellow-100 text-black font-serif">
      <header className="bg-black text-yellow-300 p-4 text-center">
        <h1 className="text-4xl font-bold">Personajes de Pulp Fiction</h1>
      </header>
      <main className="container mx-auto py-8">
        <ScrollArea className="h-[calc(100vh-8rem)] rounded-md border border-black p-4">
          <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
            {characters.map((character) => (
              <Card key={character.name} className="bg-white border-2 border-black shadow-lg hover:shadow-xl transition-shadow duration-300">
                <CardContent className="p-4">
                  <Image
                    src={character.image}
                    alt={character.name}
                    width={200}
                    height={300}
                    className="mx-auto mb-4 rounded-md border-2 border-black"
                  />
                  <h2 className="text-2xl font-bold mb-2 text-center">{character.name}</h2>
                  <p className="text-sm text-gray-700">{character.description}</p>
                </CardContent>
              </Card>
            ))}
          </div>
        </ScrollArea>
      </main>
      <footer className="bg-black text-yellow-300 p-4 text-center">
        <p>&copy; {new Date().getFullYear()} Pulp Fiction Fan Page</p>
      </footer>
    </div>
  )
}

