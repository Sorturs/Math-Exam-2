import { useState, useEffect } from 'react';
import { questions } from './data';

function App() {
  const [examQuestions, setExamQuestions] = useState([]);
  
  useEffect(() => {
    // Fisher-Yates Shuffle
    const shuffle = (array) => {
      let arr = [...array];
      for (let i = arr.length - 1; i > 0; i--) {
        const j = Math.floor(Math.random() * (i + 1));
        [arr[i], arr[j]] = [arr[j], arr[i]];
      }
      return arr;
    };
    
    setExamQuestions(shuffle(questions));
  }, []);

  return (
    <div>
      <h1>EQAO Mock Exam</h1>
      {/* Map through your shuffled examQuestions here */}
    </div>
  );
}

export default App;
