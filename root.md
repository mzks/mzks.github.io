# ROOT note

## Histgram

### Basic Draw
```cpp
//Constructer
auto h = new TH1D("name","title",bin,min,max);

//Fill
h->Fill(data);

//Draw
h->Draw();
```


## Graph
```cpp
//Prepare data
vector<Double_t> x = {1.0 ,2.0, 3.0};
vector<Double_t> y = {1.0 ,4.0, 9.0};

//Constructer
auto g = new TGraph(x.size(), x.data(), y.data());

//Draw
g->Draw();
```

## Tree

There is a root file(data.root) including TTree(mytree), which has two branch(x,y).
```cpp
//Read file
auto f = TFile::Open("./data.root");
auto t = dynamic_cast<TTree*>(f->Get("mytree"));

//Draw
t->Draw("x:y>>myhist","","colz");
```
First argument in this Draw method is branch, generating histgram.
If there is not myhist, ROOT is generating myhist automatically.
Second one is selection, third one is draw option.
