# ROOT note
Useful pages for buiginners
- [ROOT ofiisial page](https://root.cern.ch)
- [ROOT users guide](https://root.cern.ch/root/htmldoc/guides/users-guide/ROOTUsersGuide.html)

Useful pages in Japanese
- [RHEA](https://github.com/akira-okumura/RHEA)
- [Atlas japan C++ tutorial](http://www.icepp.s.u-tokyo.ac.jp/%7Esakamoto/education/atlasj/cplusplus/index.html)
- [kamono wiki](http://www-he.scphys.kyoto-u.ac.jp/member/n.kamo/wiki/doku.php?id=index)

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
