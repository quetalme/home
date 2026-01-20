import React, { useState, useEffect } from 'react';
import { MapPin, Navigation, ShoppingCart, CheckCircle, ArrowLeft, Clock, DollarSign, Phone } from 'lucide-react';

const WhatsAppWebPage = () => {
  const [loading, setLoading] = useState(true);
  const [session, setSession] = useState(null);
  const [location, setLocation] = useState(null);
  const [loadingLocation, setLoadingLocation] = useState(false);
  const [deliveryInfo, setDeliveryInfo] = useState(null);
  const [cart, setCart] = useState([]);
  const [step, setStep] = useState('menu');
  const [manualAddress, setManualAddress] = useState('');

  const urlParams = {
    token: 'abc123xyz',
    phone: '5598912345678',
    action: 'view_menu',
    source: 'whatsapp'
  };

  const menuItems = [
    {
      id: 1,
      name: 'Risoto de Funghi Porcini',
      description: 'Arroz arbóreo cremoso com cogumelos porcini',
      price: 68.00,
      image: '🍚',
      category: 'main'
    },
    {
      id: 2,
      name: 'Salmão Grelhado',
      description: 'Filé de salmão com aspargos verdes',
      price: 85.00,
      image: '🐟',
      category: 'main'
    },
    {
      id: 3,
      name: 'Tiramisù Clássico',
      description: 'Sobremesa italiana com mascarpone',
      price: 28.00,
      image: '🍰',
      category: 'dessert'
    }
  ];

  useEffect(() => {
    validateSession();
  }, []);

  const validateSession = async () => {
    setLoading(true);
    try {
      setTimeout(() => {
        setSession({
          valid: true,
          user: {
            phone: urlParams.phone,
            name: 'João Silva'
          }
        });
        setLoading(false);
      }, 1000);
    } catch (error) {
      console.error('Erro ao validar sessão:', error);
      setLoading(false);
    }
  };

  const requestLocation = async () => {
    setLoadingLocation(true);
    
    if ('geolocation' in navigator) {
      navigator.geolocation.getCurrentPosition(
        async (position) => {
          const { latitude, longitude } = position.coords;
          
          const address = await reverseGeocode(latitude, longitude);
          
          const locationData = {
            latitude,
            longitude,
            address,
            accuracy: position.coords.accuracy
          };
          
          setLocation(locationData);
          
          const delivery = calculateDeliveryInfo(latitude, longitude);
          setDeliveryInfo(delivery);
          
          setLoadingLocation(false);
          setStep('checkout');
        },
        (error) => {
          console.error('Erro ao obter localização:', error);
          alert('Não foi possível obter sua localização. Por favor, digite seu endereço manualmente.');
          setLoadingLocation(false);
        },
        {
          enableHighAccuracy: true,
          timeout: 10000,
          maximumAge: 0
        }
      );
    } else {
      alert('Geolocalização não suportada pelo navegador');
      setLoadingLocation(false);
    }
  };

  const reverseGeocode = async (lat, lng) => {
    return 'Rua das Flores, 123 - Centro, Assunção, Paraguai';
  };

  const calculateDeliveryInfo = (lat, lng) => {
    const distance = 3.5;
    return {
      distance: '3.5 km',
      fee: 'R$ 8,00',
      time: '35-45 minutos'
    };
  };

  const useManualAddress = () => {
    if (!manualAddress.trim()) {
      alert('Por favor, digite seu endereço');
      return;
    }
    
    setLocation({
      address: manualAddress,
      manual: true
    });
    
    setDeliveryInfo({
      distance: 'Calculando...',
      fee: 'R$ 10,00',
      time: '40-50 minutos'
    });
    
    setStep('checkout');
  };

  const addToCart = (item) => {
    const existing = cart.find(i => i.id === item.id);
    if (existing) {
      setCart(cart.map(i => 
        i.id === item.id 
          ? { ...i, quantity: i.quantity + 1 }
          : i
      ));
    } else {
      setCart([...cart, { ...item, quantity: 1 }]);
    }
  };

  const removeFromCart = (itemId) => {
    const existing = cart.find(i => i.id === itemId);
    if (existing.quantity === 1) {
      setCart(cart.filter(i => i.id !== itemId));
    } else {
      setCart(cart.map(i => 
        i.id === itemId 
          ? { ...i, quantity: i.quantity - 1 }
          : i
      ));
    }
  };

  const getCartTotal = () => {
    return cart.reduce((sum, item) => sum + (item.price * item.quantity), 0);
  };

  const completeOrder = () => {
    setStep('success');
    
    console.log('Pedido finalizado:', {
      cart,
      location,
      deliveryInfo,
      total: getCartTotal()
    });
  };

  const returnToWhatsApp = () => {
    const phone = session.user.phone.replace('+', '');
    const message = encodeURIComponent('Obrigado! Meu pedido foi confirmado! 🎉');
    window.location.href = `https://wa.me/${phone}?text=${message}`;
  };

  if (loading) {
    return (
      <div className="min-h-screen bg-gradient-to-br from-green-50 to-green-100 flex items-center justify-center">
        <div className="text-center">
          <div className="animate-spin text-6xl mb-4">⏳</div>
          <p className="text-gray-600">Carregando...</p>
        </div>
      </div>
    );
  }

  if (!session?.valid) {
    return (
      <div className="min-h-screen bg-gradient-to-br from-red-50 to-red-100 flex items-center justify-center p-4">
        <div className="bg-white rounded-2xl shadow-xl p-8 max-w-md text-center">
          <div className="text-6xl mb-4">❌</div>
          <h2 className="text-2xl font-bold text-gray-800 mb-2">Sessão Inválida</h2>
          <p className="text-gray-600 mb-6">
            Seu link expirou ou é inválido. Por favor, solicite um novo link no WhatsApp.
          </p>
          <button
            onClick={returnToWhatsApp}
            className="bg-green-500 text-white px-6 py-3 rounded-lg hover:bg-green-600 transition flex items-center gap-2 mx-auto"
          >
            <Phone size={20} />
            Voltar ao WhatsApp
          </button>
        </div>
      </div>
    );
  }

  return (
    <div className="min-h-screen bg-gradient-to-br from-orange-50 via-red-50 to-pink-50">
      <header className="bg-white shadow-lg sticky top-0 z-50">
        <div className="max-w-4xl mx-auto px-4 py-4">
          <div className="flex items-center justify-between">
            <div className="flex items-center gap-3">
              <span className="text-4xl">🍝</span>
              <div>
                <h1 className="text-2xl font-bold text-gray-800">Bella Tavola</h1>
                <p className="text-sm text-gray-600">Olá, {session.user.name}!</p>
              </div>
            </div>
            {cart.length > 0 && (
              <button
                onClick={() => setStep('location')}
                className="bg-orange-500 text-white px-4 py-2 rounded-lg hover:bg-orange-600 transition flex items-center gap-2"
              >
                <ShoppingCart size={20} />
                <span className="font-semibold">{cart.length}</span>
              </button>
            )}
          </div>
        </div>
      </header>

      <main className="max-w-4xl mx-auto px-4 py-6">
        {step === 'menu' && (
          <div>
            <div className="bg-green-100 border border-green-300 rounded-lg p-4 mb-6 flex items-center gap-3">
              <Phone size={24} className="text-green-600 flex-shrink-0" />
              <p className="text-green-800 text-sm">
                Você veio do WhatsApp! Escolha seus pratos e finalize seu pedido com delivery.
              </p>
            </div>

            <h2 className="text-2xl font-bold text-gray-800 mb-4">Nosso Menu</h2>
            
            <div className="grid gap-4">
              {menuItems.map(item => (
                <div key={item.id} className="bg-white rounded-xl shadow-lg p-5 flex items-center gap-4">
                  <span className="text-5xl">{item.image}</span>
                  <div className="flex-1">
                    <h3 className="text-xl font-bold text-gray-800">{item.name}</h3>
                    <p className="text-gray-600 text-sm mb-2">{item.description}</p>
                    <p className="text-2xl font-bold text-orange-600">R$ {item.price.toFixed(2)}</p>
                  </div>
                  <button
                    onClick={() => addToCart(item)}
                    className="bg-orange-500 text-white px-6 py-3 rounded-lg hover:bg-orange-600 transition font-semibold"
                  >
                    Adicionar
                  </button>
                </div>
              ))}
            </div>

            {cart.length > 0 && (
              <button
                onClick={() => setStep('location')}
                className="w-full bg-green-500 text-white py-4 rounded-xl mt-6 font-bold text-lg hover:bg-green-600 transition shadow-lg"
              >
                Continuar para Delivery ({cart.length} {cart.length === 1 ? 'item' : 'itens'})
              </button>
            )}
          </div>
        )}

        {step === 'location' && (
          <div>
            <button
              onClick={() => setStep('menu')}
              className="flex items-center gap-2 text-gray-600 hover:text-gray-800 mb-6"
            >
              <ArrowLeft size={20} />
              Voltar ao menu
            </button>

            <div className="bg-white rounded-2xl shadow-xl p-8">
              <h2 className="text-2xl font-bold text-gray-800 mb-6 flex items-center gap-3">
                <MapPin className="text-orange-500" />
                Onde você está?
              </h2>

              <p className="text-gray-600 mb-6">
                Para calcular o frete e tempo de entrega, precisamos da sua localização.
              </p>

              <button
                onClick={requestLocation}
                disabled={loadingLocation}
                className="w-full bg-blue-500 text-white py-4 rounded-xl mb-4 font-semibold hover:bg-blue-600 transition flex items-center justify-center gap-3 disabled:opacity-50"
              >
                {loadingLocation ? (
                  <>
                    <div className="animate-spin">⏳</div>
                    Obtendo localização...
                  </>
                ) : (
                  <>
                    <Navigation size={24} />
                    Usar Minha Localização Atual
                  </>
                )}
              </button>

              <div className="flex items-center gap-3 my-6">
                <div className="flex-1 border-t border-gray-300"></div>
                <span className="text-gray-500 text-sm">OU</span>
                <div className="flex-1 border-t border-gray-300"></div>
              </div>

              <div className="space-y-4">
                <input
                  type="text"
                  placeholder="Digite seu endereço completo"
                  value={manualAddress}
                  onChange={(e) => setManualAddress(e.target.value)}
                  className="w-full border border-gray-300 rounded-lg px-4 py-3 focus:outline-none focus:ring-2 focus:ring-orange-500"
                />
                <button
                  onClick={useManualAddress}
                  className="w-full bg-gray-700 text-white py-3 rounded-xl font-semibold hover:bg-gray-800 transition"
                >
                  Continuar com este endereço
                </button>
              </div>
            </div>
          </div>
        )}

        {step === 'checkout' && (
          <div>
            <button
              onClick={() => setStep('location')}
              className="flex items-center gap-2 text-gray-600 hover:text-gray-800 mb-6"
            >
              <ArrowLeft size={20} />
              Alterar endereço
            </button>

            <div className="bg-white rounded-xl shadow-lg p-6 mb-4">
              <h3 className="font-bold text-gray-800 mb-3 flex items-center gap-2">
                <MapPin className="text-green-500" />
                Local de Entrega
              </h3>
              <p className="text-gray-700">{location?.address}</p>
              {deliveryInfo && (
                <div className="mt-4 grid grid-cols-3 gap-4 text-center">
                  <div className="bg-blue-50 rounded-lg p-3">
                    <MapPin size={20} className="mx-auto text-blue-600 mb-1" />
                    <p className="text-xs text-gray-600">Distância</p>
                    <p className="font-bold text-blue-600">{deliveryInfo.distance}</p>
                  </div>
                  <div className="bg-green-50 rounded-lg p-3">
                    <DollarSign size={20} className="mx-auto text-green-600 mb-1" />
                    <p className="text-xs text-gray-600">Frete</p>
                    <p className="font-bold text-green-600">{deliveryInfo.fee}</p>
                  </div>
                  <div className="bg-orange-50 rounded-lg p-3">
                    <Clock size={20} className="mx-auto text-orange-600 mb-1" />
                    <p className="text-xs text-gray-600">Tempo</p>
                    <p className="font-bold text-orange-600">{deliveryInfo.time}</p>
                  </div>
                </div>
              )}
            </div>

            <div className="bg-white rounded-xl shadow-lg p-6 mb-4">
              <h3 className="font-bold text-gray-800 mb-4">Seu Pedido</h3>
              {cart.map(item => (
                <div key={item.id} className="flex items-center justify-between mb-3 pb-3 border-b">
                  <div className="flex items-center gap-3">
                    <span className="text-3xl">{item.image}</span>
                    <div>
                      <p className="font-semibold text-gray-800">{item.name}</p>
                      <p className="text-sm text-gray-600">R$ {item.price.toFixed(2)} x {item.quantity}</p>
                    </div>
                  </div>
                  <div className="flex items-center gap-3">
                    <button
                      onClick={() => removeFromCart(item.id)}
                      className="bg-red-100 text-red-600 w-8 h-8 rounded-full hover:bg-red-200"
                    >
                      -
                    </button>
                    <span className="font-bold">{item.quantity}</span>
                    <button
                      onClick={() => addToCart(item)}
                      className="bg-green-100 text-green-600 w-8 h-8 rounded-full hover:bg-green-200"
                    >
                      +
                    </button>
                  </div>
                </div>
              ))}

              <div className="mt-4 pt-4 border-t space-y-2">
                <div className="flex justify-between text-gray-700">
                  <span>Subtotal:</span>
                  <span className="font-semibold">R$ {getCartTotal().toFixed(2)}</span>
                </div>
                <div className="flex justify-between text-gray-700">
                  <span>Frete:</span>
                  <span className="font-semibold">{deliveryInfo?.fee || 'R$ 0,00'}</span>
                </div>
                <div className="flex justify-between text-xl font-bold text-gray-900 pt-2 border-t">
                  <span>Total:</span>
                  <span>R$ {(getCartTotal() + 8).toFixed(2)}</span>
                </div>
              </div>
            </div>

            <button
              onClick={completeOrder}
              className="w-full bg-green-500 text-white py-4 rounded-xl font-bold text-lg hover:bg-green-600 transition shadow-lg"
            >
              Finalizar Pedido
            </button>
          </div>
        )}

        {step === 'success' && (
          <div className="text-center py-12">
            <div className="bg-white rounded-2xl shadow-xl p-8 max-w-md mx-auto">
              <CheckCircle size={80} className="text-green-500 mx-auto mb-4" />
              <h2 className="text-3xl font-bold text-gray-800 mb-4">Pedido Confirmado!</h2>
              <p className="text-gray-600 mb-6">
                Seu pedido foi recebido com sucesso e já está sendo preparado!
              </p>
              
              <div className="bg-orange-50 rounded-lg p-4 mb-6">
                <p className="text-sm text-gray-700 mb-2">Tempo estimado de entrega:</p>
                <p className="text-2xl font-bold text-orange-600">{deliveryInfo?.time}</p>
              </div>

              <p className="text-gray-600 mb-6">
                Você receberá atualizações no WhatsApp sobre o status do seu pedido.
              </p>

              <button
                onClick={returnToWhatsApp}
                className="w-full bg-green-500 text-white py-4 rounded-xl font-bold hover:bg-green-600 transition flex items-center justify-center gap-3"
              >
                <Phone size={24} />
                Voltar ao WhatsApp
              </button>
            </div>
          </div>
        )}
      </main>
    </div>
  );
};

export default WhatsAppWebPage;
