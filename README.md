import React from "react";
import { Card, CardContent } from "@/components/ui/card";
import { Button } from "@/components/ui/button";
import { ShoppingCart, Heart } from "lucide-react";

const products = [
  { id: 1, name: "Suplemento Vitamínico", price: "R$ 59,90", category: "Nutrição" },
  { id: 2, name: "Kit de Cuidados com a Pele", price: "R$ 129,90", category: "Bem-estar" },
  { id: 3, name: "Óleo de Massagem Relaxante", price: "R$ 79,90", category: "Saúde Sexual" },
  { id: 4, name: "Monitor de Pressão Arterial", price: "R$ 199,90", category: "Cuidados Médicos" }
];

export default function HealthStore() {
  return (
    <div className="p-6 grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6">
      {products.map((product) => (
        <Card key={product.id} className="p-4 rounded-2xl shadow-md">
          <CardContent>
            <h2 className="text-xl font-semibold">{product.name}</h2>
            <p className="text-gray-500">{product.category}</p>
            <p className="text-lg font-bold mt-2">{product.price}</p>
            <div className="flex gap-2 mt-4">
              <Button className="flex items-center gap-2">
                <ShoppingCart size={16} /> Comprar
              </Button>
              <Button variant="outline" className="flex items-center gap-2">
                <Heart size={16} /> Favoritar
              </Button>
            </div>
          </CardContent>
        </Card>
      ))}
    </div>
  );
}
