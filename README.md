- 👋 Hi, I’m @AyeshaZafarrrr
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
const express = require('express');
const app = express();
const path = require('path');
const fs = require('fs');

const PORT = process.env.PORT || 3000;

app.use(express.static('public'));

app.get('/api/data', (req, res) => {
    // Read data from data.json (replace with your own data source logic)
    fs.readFile(path.resolve(__dirname, 'data.json'), (err, data) => {
        if (err) {
            console.error('Error reading data file:', err);
            res.status(500).json({ error: 'Internal Server Error' });
            return;
        }

        res.json(JSON.parse(data));
    });
});

app.listen(PORT, () => {
    console.log(`Server is running on http://localhost:${PORT}`);
});

<!---
AyeshaZafarrrr/AyeshaZafarrrr is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
