import React from 'react';

// Navbar component
const Navbar: React.FC = () => {
  const scrollToSection = (sectionId: string) => {
    const section = document.getElementById(sectionId);
    section?.scrollIntoView({ behavior: 'smooth' });
  };

  return (
    <nav className="bg-gray-800 text-white p-4 fixed w-full top-0 z-10">
      <ul className="flex space-x-8 justify-center">
        <li>
          <button
            onClick={() => window.location.reload()}
            className="hover:text-gray-400 transition duration-300"
          >
            Home
          </button>
        </li>
        <li>
          <button
            onClick={() => scrollToSection('about')}
            className="hover:text-gray-400 transition duration-300"
          >
            About
          </button>
        </li>
        <li>
          <button
            onClick={() => scrollToSection('services')}
            className="hover:text-gray-400 transition duration-300"
          >
            Services
          </button>
        </li>
        <li>
          <button
            onClick={() => scrollToSection('contact')}
            className="hover:text-gray-400 transition duration-300"
          >
            Contact
          </button>
        </li>
      </ul>
    </nav>
  );
};

// Cards component
const Cards: React.FC = () => {
  const cardData = [
    { title: 'Card 1', description: 'This is card 1' },
    { title: 'Card 2', description: 'This is card 2' },
    { title: 'Card 3', description: 'This is card 3' },
  ];

  return (
    <div className="grid grid-cols-1 md:grid-cols-3 gap-8 px-4 py-12">
      {cardData.map((card, index) => (
        <div
          key={index}
          className="bg-gray-700 text-white p-6 rounded-lg shadow-lg hover:scale-105 transition-transform duration-300"
        >
          <h3 className="text-xl font-bold mb-2">{card.title}</h3>
          <p>{card.description}</p>
        </div>
      ))}
    </div>
  );
};

// Main Page component
const Home: React.FC = () => {
  return (
    <div>
      <Navbar />
      <section id="home" className="h-screen bg-gray-900 flex items-center justify-center">
        <h1 className="text-white text-5xl">Welcome to My Website</h1>
      </section>
      <section id="about" className="h-screen bg-gray-800 flex items-center justify-center">
        <h2 className="text-white text-4xl">About Us</h2>
      </section>
      <section id="services" className="h-screen bg-gray-700 flex items-center justify-center">
        <h2 className="text-white text-4xl">Our Services</h2>
        <Cards />
      </section>
      <section id="contact" className="h-screen bg-gray-600 flex items-center justify-center">
        <h2 className="text-white text-4xl">Contact Us</h2>
      </section>
    </div>
  );
};

export default Home;
